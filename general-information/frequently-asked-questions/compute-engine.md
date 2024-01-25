# Compute Engine

### What are cloud servers?

The cloud server is suitable for anyone who wants a robust IT infrastructure at a reasonable price. It's the perfect foundation for various web projects, whether it's a private homepage or company website, a robust framework for web developers, or a high-performance gaming server. With the cloud servers, you can flexibly balance the necessary resources and pay only for what is actually used. If you are working on larger projects in which you use servers for different purposes, such as a front-end server with a load balancer in conjunction with database servers that you manage from third-party software via an API, then you can easily match such scenarios with the cloud server solutions. You also get unlimited traffic and high availability.

### Are cloud servers suitable for enterprise hosting?

Yes, the cloud plans provided by IONOS are ideal for small and medium businesses. Just choose the appropriate tariff for your needs based on the required server resources. They are usually differentiated by Central Processing Unit (CPU), Random Access Memory (RAM), and memory capacity. Fast Solid State Disk (SSD) with low access times is available in every plan for data transfer and storage. Whenever you need more resources, you can adjust them in real time as needed. For larger companies that need more performance and server resources, we recommend using **Compute Engine**.

### How can I change the data center location?

You can specify the location of a data center only when you provision it for the first time. Once the data center is provisioned, you can no longer change its location.

### Why can I not access my Virtual Machine (VM) via the Remote Console?

DCD Remote Console relies upon Virtual Network Computing (VNC) and requires **port 5900**. Always use the latest **Java version**. Make the following ports available in your firewall for outgoing connection requests:

 * **For HTTP:** port 80  
 * **For HTTPS:** port 443  
 * **For VNC:** port 5900 
 
 The Remote Console becomes available immediately once the provisioning of your server is complete.

### How can I find the location of my data center?

In the **DCD**, go to the **Dashboard** > **My Data Centers**. The **Region** column has the list of the location of your data center.

Alternatively, you can use the **Start Center** option to view the location of your VDCs. 
