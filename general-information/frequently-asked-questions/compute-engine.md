# Compute Engine

### What are cloud servers?

The cloud server is suitable for anyone who wants a robust IT infrastructure at a reasonable price. It is the perfect foundation for various web projects, whether it is a private homepage or company website, a robust framework for web developers, or a high-performance gaming server. With cloud servers, you can flexibly balance the necessary resources and pay only for what is actually used. 
If you are working on larger projects, you can use servers for various purposes. For example, consider you have a front-end server paired with a load balancer, along with database servers managed through third-party software using an API. In such cases, cloud server solutions offer a seamless match to address these diverse scenarios.

### Are cloud servers suitable for enterprise hosting?

Yes, the cloud plans provided by IONOS are ideal for small and medium businesses. Choose the appropriate tariff for your business needs based on the required server resources. They are usually differentiated by Central Processing Unit (CPU), Random Access Memory (RAM), and memory capacity. Fast Solid State Disk (SSD) with low access times is available in every data transfer and storage plan. Whenever you need more resources, you can adjust these resources in real-time as needed. We recommend using **Compute Engine** for larger companies needing more performance and server resources.

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

Alternatively, you can use the **Start Center** option to view the location of your Virtual Data Center. 
