
## Six Strategies for Application Deployment

Recreate: Version A is terminated then version B is rolled out.
Ramped (also known as rolling-update or incremental): Version B is slowly rolled out and replacing version A.
Blue/Green: Version B is released alongside version A, then the traffic is switched to version B.
Canary: Version B is released to a subset of users, then proceed to a full rollout.
A/B testing: Version B is released to a subset of users under specific condition.
Shadow: Version B receives real-world traffic alongside version A and doesn’t impact the response.

## Recreate
The recreate strategy is a dummy deployment which consists of shutting down version A then deploying version B after version A is turned off. This technique implies downtime of the service that depends on both shutdown and boot duration of the application.

![image](https://user-images.githubusercontent.com/40743779/188452361-0fe95ec8-1bab-488d-9359-a72cd4df53a9.png)

Pros:
Easy to setup.
Application state entirely renewed.

Cons:
High impact on the user, expect downtime that depends on both shutdown and boot duration of the application.

## Ramped
The ramped deployment strategy consists of slowly rolling out a version of an application by replacing instances one after the other until all the instances are rolled out. It usually follows the following process: with a pool of version A behind a load balancer, one instance of version B is deployed. When the service is ready to accept traffic, the instance is added to the pool. Then, one instance of version A is removed from the pool and shut down.

Depending on the system taking care of the ramped deployment, you can tweak the following parameters to increase the deployment time:

Parallelism, max batch size: Number of concurrent instances to roll out.
Max surge: How many instances to add in addition of the current amount.
Max unavailable: Number of unavailable instances during the rolling update procedure

![image](https://user-images.githubusercontent.com/40743779/188452526-dc37dc34-8bf1-46de-bcea-11cc467f043c.png)

Pros:
Easy to set up.
Version is slowly released across instances.
Convenient for stateful applications that can handle rebalancing of the data.

Cons:
Rollout/rollback can take time.
Supporting multiple APIs is hard.
No control over traffic.
Blue/Green
