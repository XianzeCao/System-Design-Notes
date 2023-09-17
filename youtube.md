# Requirements 

## Functional requirements

- stream videos
- upload videos
- search videos according to titles
- Like and dislike videos
- Add comments to videos
- View thumbnails 

## Non-functional requirements

The usual suspects but strong consistency is not required 

## Resources Estimation 

Considering the large amount of videos uploaded every minute, the following will required:

- Storage needed to store uploaded and processed content 
- Should be able to handle concurrent processing 

Covert to numbers:

- Total user : 1.5 billion
- DAU 500 million
- Average video length 5 min
- Size of an average video before processing/encoding 600MB
- Size of an average video after encoding 30MB

# High level design

![image-20230917120819033](/Users/zaccao/Library/Application Support/typora-user-images/image-20230917120819033.png)



## API design

Upload video: 

uploadVideo(user_id, video_file, category_id, title, description, tags, default_language, privacy_settings)

| **Parameter**      | **Description**                                              |
| ------------------ | ------------------------------------------------------------ |
| `user_id`          | user that is uploading the video.                            |
| `video_file`       | video file that the user wants to upload.                    |
| `category_id`      | Refers to the category a video belongs to. Typical categories can be “Entertainment,” “Engineering,” “Science,” and so on. |
| `title`            | title of the video.                                          |
| `description`      | description of the video.                                    |
| `tags`             | This refers to the specific topics the content of the video covers. The `tags` can improve search results. |
| `default_language` | This is the default language a page will show to the user when the video is streamed. |
| `privacy_settings` | This refers to the privacy of the video. Generally, videos can be a public asset or private to the uploader. |



Stream video 

streamVideo(user_id, video_id, screen_resolution, user_bitrate, device_chipset)

| **Parameter**       | **Description**                                              |
| ------------------- | ------------------------------------------------------------ |
| `screen_resolution` | The server can best optimize the video if the user's screen resolution is known. |
| `user_bitrate`      | The transmission capacity of the user is required to understand which quality of video chunks should be transferred to the client or user. |
| `device_chipset`    | Many YouTube users watch content on handheld devices, which makes it important to know the handling capabilities of these devices to better serve the users. |



Search videos

 searchVideo(user_id, search_string, length, quality, upload_date)

| **Parameter**            | **Description**                                              |
| ------------------------ | ------------------------------------------------------------ |
| `search_string`          | This is ahe string used for searching videos by their title. |
| `length` (optional)      | This is used to filter videos based on their length in terms of time. |
| `quality` (optional)     | This is used to filter videos based on the resolution, like 2048p, 1440p, 1080p, and so on. |
| `upload_date` (optional) | This is used to filter videos based on their upload date to YouTube. |



