# Youtube-to-telegram
Send latest YouTube video to Telegram channels with a button linking to the video.
Here is the full Documentation for this AppScript.

1. The `sendLatestYoutubeVideo()` function is defined. This function fetches the latest video uploaded or scheduled on a specific YouTube channel and sends a message about it to a Telegram chat.

2. The API key for the YouTube Data API and the channel ID for the channel you want to fetch videos from are defined as variables.

3. The URL for the API request is constructed using the API key, channel ID, and the maximum number of videos to return (in this case, 1).

4. The API request is sent using the `UrlFetchApp.fetch()` method and the response is stored in the `response` variable.

5. The response is parsed as a JSON object using `JSON.parse()` and stored in the `data` variable.

6. The code checks if any videos were found in the channel. If not, it logs a message and exits the function.

7. The code checks if the latest activity is a video upload or scheduled video. If not, it logs a message and exits the function.

8. The title and video ID of the latest video are extracted from the API response and stored in the `videoTitle` and `videoId` variables, respectively.

9. The code checks if a video ID was found in the response. If not, it logs a message and exits the function.

10. The URL of the latest video is constructed using the video ID.

11. The Telegram bot token and chat IDs are defined as variables.

12. The URL for sending messages to Telegram is constructed using the bot token.

13. A button is created using the `inline_keyboard` property and the URL of the latest video.

14. The message to be sent to Telegram is constructed using the video title and URL, and the button is included as `reply_markup`.

15. A loop is started to send the message to each chat ID specified in the `TELEGRAM_CHAT_IDS` array.

16. The `chat_id`, `text`, and `payload` properties for each chat ID are set, and the message is sent using the `UrlFetchApp.fetch()` method.

17. If there is an error sending the message, a log message is created. If the message is sent successfully, a log message is created.

That's it! This code fetches the latest video from a specific YouTube channel and sends a message about it to one or more Telegram chats. If there are no videos in the channel or the latest activity is not a video upload or scheduled video, the code logs a message and exits the function.
