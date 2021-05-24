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
    
          
        
          
          
