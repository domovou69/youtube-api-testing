# DESCRIPTION

This repository demonstrate the ability to perform API testing and its automation.
It contains tests for the YouTube API using Postman.
The purpose of these tests is to validate the functionality and behavior of the YouTube API endpoints.

# Testing strategy

This testing strategy outlines the key test scenarios for various YouTube API endpoints. The following endpoints and their associated test cases are covered:

1. Search Public Videos:
   Test the ability to search for public videos using different search queries.
   Validate that the search results contain the expected video data, such as title, description, and channel information.

2. Validate Video Data:
   Retrieve a specific video using its video ID.
   Verify that the returned video data matches the expected values, including title, description, duration, and view count.

3. Get Video Rating:
   Retrieve the rating information for a specific video.
   Confirm that the returned rating data reflects the current rating status, such as the number of likes and dislikes.

4. Like video:
   Ensure that the video's like count increases accordingly and validate the response to confirm the successful like operation.

5. Dislike Video:
   Dislike a specific video.
   Verify that the video's dislike count increases accordingly and validate the response to confirm the successful dislike operation.

6. Create a Top Comment:
   Add a top-level comment to a specific video.
   Check that the comment appears correctly on the video's comment section and verify the response for a successful comment creation.

7. Get Created Comment Threads for video:
   Retrieve the comment threads associated with a specific video.
   Validate that the returned comment threads include the expected comments, with correct author information and timestamps.

8. Create Sub Comment:
   Add a reply comment to an existing comment.
   Confirm that the sub comment is correctly linked to the parent comment and validate the response for a successful sub comment creation.

9. Read Subcomments List:
   Retrieve the list of subcomments for a specific comment.
   Verify that the returned subcomments contain the expected data, such as author information, timestamps, and content.

10. Update Subcomment:
    Modify the content of a subcomment.
    Ensure that the updated subcomment reflects the changes made and validate the response for a successful subcomment update.

11. Delete Subcomment:
    Remove a subcomment from a video's comment section.
    Confirm that the subcomment is no longer visible and validate the response for a successful subcomment deletion.

12. Subscribe to Channel:
    Subscribe to a specific YouTube channel.
    Verify that the channel's subscription count increases, and validate the response for a successful subscription.

13. Get Channel Subscription Info:
    Retrieve the subscription information for a channel.
    Validate that the returned data includes the correct channel subscription details, such as the subscriber count and subscription status.

14. Unsubscribe from Channel:
    Unsubscribe from a previously subscribed YouTube channel.
    Confirm that the channel's subscription count decreases, and validate the response for a successful unsubscription.
    By implementing and executing these test cases, you can ensure that the YouTube API endpoints are functioning correctly and that the expected behaviors and data are returned in response to different requests.

# Implementation Description

The tests are written in JavaScript using the Postman tool. You can run the tests in two different ways:

# Case 1: Postman

Import the provided collection and environment variables into Postman:

Collection: YouTube.postman_collection.json
Environment Variables: API_YouTube.postman_environment.json
Make sure to set your own access token for the 'bearerToken' in the API_YouTube.postman_environment.json file.
Generate access token: https://stevesie.com/docs/pages/youtube-oauth-access-token

Execute the tests by sending the requests in Postman in a row. The tests are defined in the "Tests" tab of each request, where you can find JavaScript code using the Chai Assertion Library to validate the responses.

# Case 2: Command Line

Install the required dependencies by running the following command:

- npm install
- npm install -g newman-reporter-html

To run the tests from the command line, use the following command:

- newman run collection/YouTube.postman_collection.json -e enviromentVars/YouTube.postman_environment.json -r html --reporter-html-template reporter/colored-template.hbs

This command will execute the tests using Newman, a command-line collection runner for Postman. The HTML reporter will generate a report with the test results.

Open the generated HTML report located in the 'newman' folder to view the test results.

# Note:

Make sure to set your own values for the 'bearerToken' in the YouTube.postman_environment.json file before running the tests.
Generate access token: https://stevesie.com/docs/pages/youtube-oauth-access-token
These values are necessary for authentication and authorization purposes.
