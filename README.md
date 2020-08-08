basic docker setup for dev and prod env for a project with react front end and node backend with postgres DB, a worker process (to calc fibonacci sequence based on a subscription from the redis store and put the result of fibonacci back into redis store) and a redis service.

Basic project working:
Front end will send an index to calculate the fibonacci value for the index.
The index will be saved in DB and also added to the redis.
When the index is added to redis, the subscription by worker process will receive the index and calc the value for the index and again update the redis for that index. Finally the calc value will be sent as response.

Nginx:
Nginx sits at the front and redirects traffic to client or server based on the presence/absence of 'api' in url.