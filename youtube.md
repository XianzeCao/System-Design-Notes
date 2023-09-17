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



## 





