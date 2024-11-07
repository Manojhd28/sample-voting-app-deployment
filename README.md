Microservice - Voting App Architecture

Sample Voting application which provides interface by user for voting and other interfaces for results

Redis: Voting app for voting and stored voting at redisDb  and worker worker for read vote from redisDB

PostgeSQL: Worker app updated with the total count of vote, and also accessed by result app for read total count of vote

Goals:
1	Deploy Pod
2	Enable Connectivity
3	External Access

The overall structure of the application is straightforward. End-users interact with the application via the "voting-app" microservice. Redis receives the vote, and passes it along to the Worker microservice. 

The Worker microservice stores the vote into PostgreSQL, and the results are viewable to the end-user via the "result-app" microservice.
Your job is to translate application requirements into Kubernetes objects, so you can deploy the entire application.

https://drive.google.com/file/d/1VR95hKV7zkIOjfhRotgNYmnwCHCj0YGv/view?usp=sharing
