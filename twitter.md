Requirements

    functional

    actions on tweet: post, delete, like/dislike, reply, search, retweeet
    actions on user: view user or home timeline, follow/unfollow 

    non-functional

    availability:  some use twitter to send out time-sensitive info(service outage message etc.) therefore good uptime percentage required
    latency: tweet distribution must have low latency, latency to show home timeline could be a little high
    scalability: read-heavy , write to read ratio is estimated to be 1:1000, but high storage capacity still needed
    consistency: effective technique is needed to offer rapid feedback to the user in the same region but evetually all users worldwide will see the update

Building blocks

    DNS
    Load balancers 
    Sequencers:  generate the unique IDs for the Tweets.
    Databases 
    Blob: stores store the images and video clips attached with the Tweets.
    Key-value stores: for multiple purposes such as indexing, identifying the specified counter to update its value, identifying the Tweets of a particular user and many more.
    Pub-sub: used for real-time processing such as elimination of redundant data, organizing data, and much more.
    Sharded counters: help to handle the count of multiple features such as viewing, liking, Retweeting etc
    Cache 
    CDN 
    Monitoring 


Detailed Design 
    
    Storage system: verious storage models used for different services to take advantage of each model.
        Google could 

