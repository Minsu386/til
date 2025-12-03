Azure Application Gateway is an application-level routing and load balancing service

Application gateway operates on OSI Layer 7, also known as the Application layer. 
- **Azure Web Application Firewall (WAF)** policies can be attached to an Application Gateway to provide additional security
An Application Gateway is composed of Frontends, Routing Rules, and Backends:
    **Frontends** you choose an address type
        - **Private IP** will create an Internal Load Balancer
        - **Public IP** will create a Public/External Load Balancer
    **Backends** you create Backend Pools
        - Backend Pools
            - A backend pool is a collection of resources to which your application gateway can send traffic.
            - A backend pool can contain, VMs VM scale sets, IP Addresses, domain names, App Service
    **Routing Rules** are composed of **Listeners, Backend targets, HTTP Settings**
        - **Listeners** "listens" on a specified port and IP address for traffic that uses a specified protocol.
            - If the listener criteria are met, the application gateway will apply this routing rules
            - There are 2 types of listeners:
                - Basic: Forward all requests for any domain to backend pools
                - Multi-Site: Forward requests to different backend pools based on host header and host name
                - Requests are matched according to the order of the rules and the type of listener
                - Add your basic listeners last otherwise it will capture all requests
        **Backend targets** Choose where a route should go either **Backend Pool** or **Redirection**
            - To create a rule for Backend Pool you need to create **HTTP Setting**
                - Defines how we want to handle cookies, connection draining, port request time out and more. 