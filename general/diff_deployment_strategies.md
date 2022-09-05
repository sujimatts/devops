
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
  - Easy to setup.
  - Application state entirely renewed.

Cons:
  - High impact on the user, expect downtime that depends on both shutdown and boot duration of the application.

## Ramped
The ramped deployment strategy consists of slowly rolling out a version of an application by replacing instances one after the other until all the instances are rolled out. It usually follows the following process: with a pool of version A behind a load balancer, one instance of version B is deployed. When the service is ready to accept traffic, the instance is added to the pool. Then, one instance of version A is removed from the pool and shut down.

Depending on the system taking care of the ramped deployment, you can tweak the following parameters to increase the deployment time:

Parallelism, max batch size: Number of concurrent instances to roll out.
Max surge: How many instances to add in addition of the current amount.
Max unavailable: Number of unavailable instances during the rolling update procedure

![image](https://user-images.githubusercontent.com/40743779/188452526-dc37dc34-8bf1-46de-bcea-11cc467f043c.png)

Pros:
  - Easy to set up.
  - Version is slowly released across instances.
  - Convenient for stateful applications that can handle rebalancing of the data.

Cons:
  - Rollout/rollback can take time.
  - Supporting multiple APIs is hard.
  - No control over traffic.
  - Blue/Green

## Blue/Green
The blue/green deployment strategy differs from a ramped deployment, version B (green) is deployed alongside version A (blue) with exactly the same amount of instances. After testing that the new version meets all the requirements the traffic is switched from version A to version B at the load balancer level.

![blue-green](https://user-images.githubusercontent.com/40743779/188453166-9fce0368-d629-4423-8825-ab890e9303d3.gif)


Pros:
  - Instant rollout/rollback.
  - Avoid versioning issue, the entire application state is changed in one go.

Cons:
  - Expensive as it requires double the resources.
  - Proper test of the entire platform should be done before releasing to production.
  - Handling stateful applications can be hard.

## Canary
A canary deployment consists of gradually shifting production traffic from version A to version B. Usually the traffic is split based on weight. For example, 90 percent of the requests go to version A, 10 percent go to version B.

This technique is mostly used when the tests are lacking or not reliable or if there is little confidence about the stability of the new release on the platform.

![canary](https://user-images.githubusercontent.com/40743779/188453339-fdc901ee-8a4b-4b9b-8757-1383e0704a0c.gif)

Pros:
  - Version released for a subset of users.
  - Convenient for error rate and performance monitoring.
  - Fast rollback.

Con:
  - Slow rollout.

## A/B testing
A/B testing deployments consists of routing a subset of users to a new functionality under specific conditions. It is usually a technique for making business decisions based on statistics, rather than a deployment strategy. However, it is related and can be implemented by adding extra functionality to a canary deployment so we will briefly discuss it here.

This technique is widely used to test conversion of a given feature and only roll-out the version that converts the most.

Here is a list of conditions that can be used to distribute traffic amongst the versions:

  - By browser cookie
  - Query parameters
  - Geolocalisation
  - Technology support: browser version, screen size, operating system, etc.
  - Language

![ab](https://user-images.githubusercontent.com/40743779/188453549-ac080d80-977d-4044-9fde-8d5d9f4b8f64.gif)


Pros:
  - Several versions run in parallel.
  - Full control over the traffic distribution.

Cons:
  - Requires intelligent load balancer.
  - Hard to troubleshoot errors for a given session, distributed tracing becomes mandatory.

## Shadow
A shadow deployment consists of releasing version B alongside version A, fork version A’s incoming requests and send them to version B as well without impacting production traffic. This is particularly useful to test production load on a new feature. A rollout of the application is triggered when stability and performance meet the requirements.

This technique is fairly complex to setup and needs special requirements, especially with egress traffic. For example, given a shopping cart platform, if you want to shadow test the payment service you can end-up having customers paying twice for their order. In this case, you can solve it by creating a mocking service that replicates the response from the provider.

![shadow](https://user-images.githubusercontent.com/40743779/188453765-9c54e232-deb4-4059-ae39-e39cfa8c5049.gif)

Pros:
  - Performance testing of the application with production traffic.
  - No impact on the user.
  - No rollout until the stability and performance of the application meet the requirements.

Cons:
  - Expensive as it requires double the resources.
  - Not a true user test and can be misleading.
  - Complex to setup.
  - Requires mocking service for certain cases.


REFER: https://thenewstack.io/deployment-strategies/
