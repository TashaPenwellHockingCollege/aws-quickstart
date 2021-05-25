# Section 1 - Elastic Load Balancing
* Distributes incoming application or network traffic across multiple targets in a single AZ or across multiple AZ
        -Targets can include EC2 instances, containers, IP addresses and Lambda functions
* Scales your load balancer as traffic to your application changes over time
        -Can auto scale to most workloads
        
* Three Types of Elastic Load Balancers
   1.  Application Load Balancer
          -operates at application level or Level 7 of the OSI model
          -routes traffic to targets based on content of the request
          -ideal for advanced loads balancing of HTTP and HTTPS traffic
          -Application load balancer provides advanced request routing that is targeted at delivery of modern application architectures, including microservices and container-based applications
          -Application Load Balancer simplifies and improves the security of your application by ensuring that latest secure sockets layer and transport security layer ciphers and protocols are used at all times
   2.  Network Load Balancer
          -operated at Network transport level or Level 4 of OSI model
          -routes connections to targets based on IP protocol data
          -works well for load balancing both TCP and UDP traffic
          -capabile of handling millions of rquests per second 
          -maintains ultra low latencies
          -optimized to handle sudden and volatile network traffic patterns
                    
   3.  Classic Load Balancer (Previous Generation)
          -Classic load balancer provides basic load balancing across multiple EC2 isntances
          -Operates at both the application level and network transport level
          -supports the load balancing of applications that use HTTP/S, TCP and SSL protocols
          -older implementation and AWS recommends use a dedicated application load balancer or network load balancer
          
* How Elastic Load Balancing Works
    -Accepts incoming traffic from clients, a routes request to its registered targets in one ore more AZ
    -Configure load balancer to accept incoming traffic by specifying one or more listeners
    -with Application or Network Load Balancer, you register targets in target groups and route traffic to the target groups
    -with Classic Load Balancer, you register instances w/ the load balancer
    -a listener is a process that checks for connection requests
    
* Use Cases for Elastic Load Balancers
     - Highly available and fault-tolerant applications
     - Containerized applications
     - Elasticity and scalability
     - VPC
     - Hybrid environments
     - Invoke Lambda functions over HTTPS
* Load Balancer Monitoring
     - Amazon CloudWatch metrics:  used to verif that the system is performing as expected and creates an alarm to initiate an action if a metric goes outside of acceptable range
     - Access Logs:  Capture detailed information about requests sent to your load balancer
     - AWS CloudTrail Logs - Capture the who, what, when, and where of API interactions in AWS services
    
# Section 2:  Amazon CloudWatch
        * monitoring adn observability service
        * built for dev ops engineers, developers, site reliability engineers, and IT managers
        *MONITORS
                -AWS resources
                -Applications that run on AWS
        *COLLECTS AND TRACKS
                -standard metrics
                -custom metrics
        *ALARMS
                -send notifications to Amazon SNS topic
                -perform EC2 Auto Scaling or EC2 actions
                -ex:  CPU utilization , Elastic Load Balancing rquests, DynamoDB, etc.
                -can be based on custom metrics
        *EVENTS
                -define rules to match changes in AWS environment and route these events to one or more target functions or streams for processing
                -targets can include EBS, SQS, etc.
        *pay for what you use
        *CLOUDWATCH ALARMS
                -Create alarms based on
                        1.  Static threshold
                        2.  Anomaly detection
                        3.  Metric math expression
                -Specify (must specify when set alarm)
                        1.  Namespace
                        2.  Metric
                        3.  Statistic
                        4.  Period
                        5.  Conditions
                        6.  Additional configuration
                        7.  Actions
        * for monitoring AWS resources
                -i.e. How do you know when you should launch more EC2 instances?
                      Is your application's performance/availability being affect by lack of sufficient capacity?
                      How much of your infra do you actually use?

# Section 3 - EC2 Auto Scaling
        * WHY IS SCALING IMPORTANT?
                -prevent underutilization of resources (not using all resources paying for)
                -prevent unavailability of resources (not enough resources for demand)
        * EC2 AUTO SCALING
                - helps you maintain application availability
                -enables you to auto add/remove EC2 instances according to conditions that you define manually, on a schedule or in response to changing demand or in combo w/ Auto Scaling for Predictive Scalying
                -Automatic Scaling is useful for predictable workloads
                -Auto scaling is useful for dynamic, on-demand scaling
                -AUTO SCALING GROUP:  collection of EC2 instances that are treated as a logical grouping for purposes of automatic scaling and management
                        -can specify the minimum number of instances in each Auto Scaling Group and EC2 instances that are treated as a logical grouping for the purpose of auto scaling and management
                -detects impaired EC2 instances and unhealthy applications and replaces the instance without your intervention
                -Provides several scaling options - Manual, scheduled, dynamic or on-demand and predictive
                -can use Fleet Management features of EC2 Auto Scaling to mainting the health adn availability of fleet
        *SCALING OUT
                -launching EC2 instances
        *SCALING IN
                -terminating EC2 instances
        *HOW AUTO SCALING WORKS
                -to launch EC2 instances, an Auto Scaling group uses a launch configuration.
                        -LAUNCH CONFIGURATION:  instance configuration template
                -when create a launch config you specify what information instances will use when scaling
                        -info to specify (the WHAT)
                                1.  ID of the AMI
                                2.  Instance type
                                3.  IAM roles
                                4.  One or more security groups
                                5.  any EBS volumes
                        -info on WHERE to scale
                                - define the minimum and maximum number of instnaces and desired capacity of Auto Scaling Group --> then launch it into a subnet w/in a VPC
                                -Integrates w/ Elastic Load Balancing to enable to attach one or more load balancers to an existing Auto Scaling Group --> after attach load balancer it auto register the instances in a group --> and distributes incoming traffic across those instances
                        -specify WHEN want to scale
                                -MAINTAIN CURRENT NUMBER:  can Auto Scaling Group to maintain specified number of running instances at all times; can do health checks on isntances and terminate unhealthy ones and auto start new one
                                -MANUAL SCALING:  you specify only the change in the max adn min of desired capacity of Auto Scaling Group
                                -SCHEDULED SCALING:  scaling actions are performed auto as a function of date and time.  Useful for predictable workloads
                                -DYNAMIC ON DEMAND SCALING:  more advanced way to scale resources where you define parameter that control the scaling processing using scaling policies
                                        -can use Amazon CloudWatch to check for CPU utilization and only scale w/ CPU utilization is breached; useful for scaling in response to changing conditions when don't know when conditions will change
                                -PREDICTIVE SCALING: can use EC2 Auto Scaling w/ AWS Scaling to implement predictive scaling; capacity scales based on predicted demand; uses data that is collected from EC2 instance usage and data is further informed by billions of data points that are drawn from our own observations
                -AWS uses well trained ML models to predict expected traffic and EC2 usage
                        --including daily and weekly patterns
                        --needs at least a day of historical data to start making predictions
                        --reevaluated every 24 hours to create a forecast for next 48 hours
                        --predictin process produces a scaling plan that can drive one or more groups automatically for EC2 instances
                        --one common config for implementing DYNAMIC SCALING is creating a CloudWatch alamr that is based on performance information collected from EC2 instances or load balancers
                                ---when performance threhold is breached a CloudWatch alarm triggers and auto scaling event that either scales out or in EC2 instances     
                        
        
          
          
