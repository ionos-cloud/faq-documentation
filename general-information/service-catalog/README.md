---
description: >-
  The Service Catalog is the central source of information about the services
  IONOS Cloud offers to its customers.
---

# Service Catalog

## Scope of Validity

The Service Catalog is the central source of information about the services IONOS Cloud offers to its customers. This document offers details on the worldwide provision and operation of all services provided by IONOS Cloud (hereinafter referred to as IONOS). It is valid for IONOS SE and its national affiliates.

## IONOS Cloud Compute Engine

Under the term “Compute Engine”, IONOS Cloud offers its customers "Infrastructure as a Service" (IaaS) in the form of virtual computing, data storage and network resources. The customer is able to make use of these resources on a flexible basis as required. The resources used (cores, RAM, storage) are billed to the customer by the minute based on a price list, which is valid at the time. Billing of external data transfers is based on data volume.

The customer performs the hiring and returning of resources. IONOS Cloud provides interfaces for this purpose, so that the customer can control the resources in flexible manner.

**IONOS Cloud Compute Engine model**

![](../../.gitbook/assets/service-catalog-infrastructure.png)

### **Data Center Designer**

IONOS Cloud provides the customer with access to a personalized web application called the “Data Center Designer” (DCD). The DCD can be accessed via modern Internet browsers. Specifically, the DCD allows the customer to both control and manage the services or sub-services provided by IONOS Cloud, including:

* Creating, editing and deleting virtual data centers
* Creating, (re-)starting, stopping, and deleting virtual servers, including optional storages
* Configuring / modifying existing virtual servers, including optional storages
* Creating, editing and deleting snapshots
* Uploading, editing, using and deleting private images
* Reserving and managing static public IP addresses
* Creating and managing private and public LANs including firewall setups
* Creating and managing SSH keys
* Management of integrated Cloud services (IONOS Cloud S3 Object Storage, IONOS Cloud Managed Kubernetes, IONOS Cloud Backup)

### **Multi-User Management**

#### Account Types

The authentication on the Data Center Designer requires that an account is assigned at least one user name and one password. There are three distinct types of accounts:

* **Contract Owner** – This account is created automatically for the user who initially registered with IONOS Cloud. Only one "Contract Owner" account can exist per contract made with IONOS Cloud. A “Contract Owner” is authorized to fully access all resources, create and delete “User” accounts and assign an “Administrator” role to them.
* **Administrator** - This role has the same privileges as the "Contract Owner", except this account type is restricted from changing the payment method of the contract. “Administrators” can assign “Administrator” roles to “User” accounts. It is possible to revoke the "Administrator" role after it has been assigned.
* **User** - This is the most basic account type. “Contract Owner” and "Administrator" account types can create or delete an unlimited number of accounts of the "User" type. This account type can be upgraded to the "Administrator" role and assigned specific privileges.

#### Resource Authorization

Multi-User Management controls access to the following resources types:

* Virtual Data Centers
* Snapshots
* Images
* IP Blocks
* Backup Units
* Kubernetes Clusters

The assigning of rights is based on Groups. A Group contains one or several “User” accounts. A “User” account can be a member of several Groups. "Contract Owner" or “Administrator” accounts do not need to be managed in groups as they have access to all contracted resources.

Multi-User Management distinguishes between the following authorizations for resources:

* **Read** – The resource and the objects they contain are visible. The attributes of objects can be displayed. The resource and the object it contains cannot be changed, nor can additional objects be added. The read authorization is implicit as soon as a group is assigned to a resource.
* **Edit** – The resource and the objects they contain are visible. The attributes of objects can be displayed and changed. The resource and the objects they contain can be deleted.
* **Sharing** – Authorizations for access to the resource can be changed.

#### Group Rights

The following group rights can be configured per group:

* **Create Data Center**: create new virtual data centers
* **Create Snapshots**: create snapshots of storages for which the group members hold at least “read” authorization
* **Reserve IP Blocks**: reserve additional IP blocks and / or give back IP blocks, which are available to the group members via the “edit” authorization
* **Create Internet Access**: Allows provisioning of public LANs inside a virtual data center
* **Use Object Storage**: access IONOS Cloud S3 Object Storage
* **Create Backup Units**: create new Backup Unit account for backup agent registration and activation
* **Create Kubernetes Clusters**: create new Kubernetes clusters
* **Access Activity Log**: view Activity Logs for the entire contract

### Two-Factor Authentication

For every account that is configured for access to the IONOS Cloud DCD (“Contract Owner”, "Administrator" or “User”), the use of 2-Factor Authentication can optionally be configured with a one-time password pursuant to RFC 6238 TOTP. 2-Factor Authentication provides increased security during the login process. In addition to their user name and password, when they log in, they are required to provide a code, which is generated using a special application (an “authenticator”).

Each account type can activate or deactivate this option in the DCD > Account management > Security for the respective account.

“Contract Owner” type accounts can set Two-Factor Authentication as a mandatory requirement for "Administrator" and “User” type accounts.

### SSH Key Support

Prior to provisioning, customers can inject the public part of an SSH key prior to provisioning using the IONOS Cloud DCD or Cloud API (version 2.0 or higher) in order to create an SSH login for storage volumes based on a public IONOS Cloud Linux image. This feature is not available for snapshots, private images, Windows OS images or MS SQL images provided by IONOS Cloud.

In DCD, it is possible to store up to 100 public SSH keys for later re-use. It is possible to mark individual SSH key as "default" which are applied to every provisioning automatically if previous mentioned requirements are fulfilled. Independent from the SSH key store, customers can also add SSH keys ad-hoc which they did not have previously stored. It is not possible to share access to a SSH key store across multiple users. Each user has access to their own SSH key store independent of their account role.

In Cloud API, it is only possible to add SSH keys ad-hoc. The SSH key store can't be accessed in this manner.

### Remote Console

A HTML5 Remote Console is available for every provisioned server via the DCD or the Cloud API. The Remote Console allows the customer complete access to the server's monitor, mouse and keyboard. The customer has access to his server with the Remote Console even in the absence of SSH or RDP connectivity.

The HTML5 Remote Console has been developed for browsers that do not support Java. It uses HTML5 and JavaScript, which makes it independent of third party software or additional installations since all it requires is a modern browser.

### IONOS Cloud APIs

#### Auth API

Every IONOS Cloud API requires authentication. Most IONOS Cloud APIs support authentication via basic authentication (username + password) or JSON Web Token (JWT) authentication. The "Telemetry API" only supports JWT authentication.

The IONOS Cloud S3 API uses its dedicated authentication with S3 credentials (key + secret) that can be retrieved via DCD or Cloud API.

The Auth API facilitates creation, management and deletion of JSON Web Tokens.

| Scope                  | URL                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------- |
| Auth API Documentation | [https://api.ionos.com/docs/authentication/](https://api.ionos.com/docs/authentication/) |
| Auth API Endpoint      | [https://api.ionos.com/auth/v1/](https://api.ionos.com/auth/v1/)                         |

#### Cloud API

IONOS Cloud provides the customer with an Application Programming Interface (API). This API gives the customer automated control over the functions from the DCD. Upon request, IONOS Cloud will provide an API reference along with example software (Cloud-CLI) on how the Cloud API can be used (links below).

IONOS Cloud provides access to the Cloud functionality for developers based on REST (Representational State Transfer). All account types are able to use the Cloud API.

| Scope                   | URL                                                                      |
| ----------------------- | ------------------------------------------------------------------------ |
| Cloud API Documentation | [https://api.ionos.com/docs/cloud/](https://api.ionos.com/docs/cloud/)   |
| Cloud API Endpoint      | [https://api.ionos.com/cloudapi/v6/](https://api.ionos.com/cloudapi/v6/) |

#### Reseller API

The Reseller API allows the customer to manage contracts and their associated admin users. The API allows resellers to create/update/delete subcontracts and update contract resource limits. New contract administrators can also be created, updated and deleted using the Reseller API.

| Scope                      | URL                                                                          |
| -------------------------- | ---------------------------------------------------------------------------- |
| Reseller API Documentation | [https://api.ionos.com/docs/reseller/](https://api.ionos.com/docs/reseller/) |
| Reseller API Endpoint      | [https://api.ionos.com/reseller/](https://api.ionos.com/reseller/)           |

#### Activity Log API

The Activity Log API allows the customer the retrieval of a list of activities conducted either in the DCD or in the Cloud API within a specific IONOS Cloud contract. Accounts of the type "Contract Owner" and "Administrator” are authorized by default to access the Activity Log API and are permitted to grant access to the Activity Log API for the "User" type accounts.

| Scope                          | URL                                                                                |
| ------------------------------ | ---------------------------------------------------------------------------------- |
| Activity Log API Documentation | [https://api.ionos.com/docs/activitylog/](https://api.ionos.com/docs/activitylog/) |
| Activity Log API Endpoint      | [https://api.ionos.com/activitylog/v1/](https://api.ionos.com/activitylog/v1/)     |

#### Billing API

The Billing API enables “Contract Owner” type accounts to check current usage and latest invoices of their IONOS Cloud account.

| Scope                      | URL                                                                        |
| -------------------------- | -------------------------------------------------------------------------- |
| Reseller API Documentation | [https://api.ionos.com/docs/billing/](https://api.ionos.com/docs/billing/) |
| Reseller API Endpoint      | [https://api.ionos.com/billing/](https://api.ionos.com/billing/)           |

#### Monitoring API

The Monitoring API allows management of alarms and alerts of the Monitoring Service as well as retrieving a list of events that got triggered by monitoring. It does not return monitoring metrics which are provided by the Metrics API (see next entry).

Please note that the Monitoring API runs in the path of CloudAPI but without an explicit version tag.

| Scope                        | URL                                                                                      |
| ---------------------------- | ---------------------------------------------------------------------------------------- |
| Monitoring API Documentation | [https://api.ionos.com/docs/monitoring/](https://api.ionos.com/docs/monitoring/)         |
| Monitoring API Endpoint      | [https://api.ionos.com/cloudapi/monitoring/](https://api.ionos.com/cloudapi/monitoring/) |

#### Telemetry API

The Telemetry API allows retrieval of metric data collected by the monitoring service. This API requires authentication via JWT (see AuthAPI above) and does not support basic authentication.

| Scope                       | URL                                                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Telemetry API Documentation | [IONOS Cloud Documentation](https://docs.ionos.com/monitoring-as-a-service/how-to-access-maas-via-api#telemetryapi) |
| Telemetry API Endpoint      | [https://api.ionos.com/telemetry/api/v1](https://api.ionos.com/telemetry/api/v1)                                    |

#### S3 Object Storage API

IONOS Cloud S3 Object Storage API requires authentication with S3 specific key + secret credentials which can be retrieved as well as managed via DCD or CloudAPI. It has specific endpoints per location. Further details are provided in the chapter "[IONOS Cloud S3 Object Storage](../../broken-reference/)".

### Virtual Data Center

On the IONOS Cloud platform, the customer can create so-called “Virtual Data Centers” (VDC). A VDC is a repository for all infrastructure resources ordered by the customer. Access to the resources in a VDC – similarly to operating a physical data center – is only possible via a corresponding network or internet connection. Within a VDC, the IONOS Cloud software allows for the distribution of various resources to different availability zones.

IONOS Cloud provides the customer with the flexibility to change the ownership of the VDC. Any IONOS Cloud customer who is a billing contract owner has the capability of transferring the ownership of a VDC created under the scope of his account with all related rights and responsibilities to any other customer having a billing contract with IONOS Cloud. In order to change the ownership of his VDC the customer is requested to contact the 24/7 Enterprise Level Support.

### Virtual Server

The customer can lease various resources from IONOS Cloud and combine them into a virtual server. Within a VDC, different resources can be distributed across different availability zones. A virtual server consists of the following components:

* Processor cores
* Memory (RAM)
* Network interface cards NIC (optional)
* Storage volumes (optional)
* CD-ROMs (optional)

Virtual servers can boot from a storage volume, a CD-ROM, or a NIC.

Furthermore, customers can configure their virtual servers via advanced settings, referred to as “Live Vertical Scaling” (LVS). LVS lets the customer add further resources to a virtual server while the operating system is in use. The scaling of resources without having to restart a virtual server can be applied as follows:

* Upscaling: CPU, RAM, NICs, storage volumes
* Downscaling: NICs, storage volumes

For IONOS Cloud provided public Images LVS is activated by default. LVS capabilities on private images and snapshots can be changed before applying them to new instances. The Image Manager provides edit functionality to these properties. Linux supports all standard LVS functions, Windows server instances, however, only support upscaling of CPU, NICs and storage volumes, and downscaling of NICs at this time. LVS for RAM is possible starting from 1 GB RAM and in full increments of GB.

Possible configurations of a virtual server are presented in the table below:

**AMD Processors:**

| Components                           | Minimum     | Maximum      |
| ------------------------------------ | ----------- | ------------ |
| Processor core (core)                | 1 core      | 62 cores     |
| Random access memory (RAM)\*         | 0.25 GB RAM | 230 GB RAM   |
| PCI Slots (NICs and storage volumes) | 0 PCI Slots | 24 PCI Slots |
| CD-ROM                               | 0 CD-ROM    | 2 CD-ROMs    |

_\* Increment/decrement of 1 GB when LVS is activated, RAM expansion beyond the defined maximum size possible on request._

**Intel Processors:**

| Components                           | Minimum     | Maximum      |
| ------------------------------------ | ----------- | ------------ |
| Processor core (core)                | 1 core      | 51 cores     |
| Random access memory (RAM)\*         | 0.25 GB RAM | 230 GB RAM   |
| PCI Slots (NICs and storage volumes) | 0 PCI Slots | 24 PCI Slots |
| CD-ROM                               | 0 CD-ROM    | 2 CD-ROMs    |

_\* Increment/decrement of 1 GB when LVS is activated, RAM expansion beyond the defined maximum size possible on request._

#### Core

IONOS Cloud lets the customer to assign appropriate processing power in the form of cores. IONOS Cloud will allocate these exclusively to the virtual server specified by the customer.

| Model           | AMD Opteron | <p>Intel Xeon<br>(Haswell / Broadwell)</p> | <p>Intel Xeon<br>(Skylake)</p> |
| --------------- | ----------- | ------------------------------------------ | ------------------------------ |
| Use             | Exclusive   | Exclusive                                  | Exclusive                      |
| Clock frequency | 2.8 GHz     | 2.1/2.4 GHz                                | 2.1 GHz                        |

The different data center locations may be equipped with different CPU models. If the CPU model is listed below, but not displayed on the contract, please contact the IONOS Cloud support team for further assistance.

| Location       | AMD Opteron | <p>Intel Xeon</p><p>(Haswell / Broadwell)</p> | <p>Intel Xeon</p><p>(Skylake)</p> |
| -------------- | ----------- | --------------------------------------------- | --------------------------------- |
| Berlin (DE)    | -           | -                                             | yes                               |
| Frankfurt (DE) | yes         | yes                                           | yes                               |
| Karlsruhe (DE) | yes         | yes                                           | -                                 |
| Logroño (ES)   | -           | -                                             | yes                               |
| London (UK)    | -           | -                                             | yes                               |
| Las Vegas (US) | yes         | yes                                           | -                                 |
| Newark (US)    | yes         | yes                                           | -                                 |

**AMD Core**

The AMD cores IONOS Cloud provides are AMD Opteron processors, optimized for high performance within Cloud infrastructure.

Current processor design allows for a high number of cores within one host system. Therefore, virtual instances may have up to 62 AMD cores.

**Intel Core**

The Intel cores IONOS Cloud provides are Intel Xeon processors that enable simultaneous computing of two threads or sets of instructions.

For each physically present processor core, the operating system addresses two virtual cores and shares the workload between them. This so-called hyper-threading approximates a system with two physical cores.

While hyper-threading can improve data processing performance, in order to exploit the benefits, it relies on the software to support the use of multiple processors. Current versions of Windows and Linux support this feature and can benefit from it.

#### Host Systems

A large number of host systems are kept ready at each location for operating virtual servers for the customers. Each host server is redundantly connected to the InfiniBand network. The host systems are assembled by the manufacturers based on our specifications and then delivered to the site.

### IONOS Cloud Cubes

Cubes are a separate type of virtual machines. While Virtual Servers use Cores exclusively, IONOS Cloud Cubes share them with other Cubes instances and exposes virtual CPUs (vCPU). Still, these virtual machines are fully isolated and separated so that no data is accessible by any other virtual machine running on the same physical core.

In addition, Cubes are delivered with one NVMe storage, that is directly attached to the physical server unit. This block storage device utilizes one of the PCI slots available by default.

IONOS Cloud Cubes is designed for cost optimization and workloads for which failover gets realized by the application and not the infrastructure. IONOS Cloud Cubes is currently rolled out to all European locations but may not be available to specific virtual data centers even if the feature is announced for availability in a particular location. Due to technical dependencies, IONOS Cloud Cubes may not be available for all legacy virtual datacenters in the location Frankfurt. The product should be available for new created virtual datacenters. Currently, IONOS Cloud Cubes are released in:

* Berlin (Germany)
* Frankfurt (Germany)
* London (UK)
* Logroño (Spain)

A Cubes instances consists of the following components

* Virtual CPUs
* Memory (RAM)
* Network interface cards NIC (optional)
* Direct Attached NVME Storage volume (mandatory)
* Block Storage volumes (optional)
* CD-ROMs (optional)

In comparison to Virtual Servers, IONOS Cloud Cubes get ordered by pre-defined instance size templates and cannot be configured in a full flexible model.

| Name      | vCPU | RAM   | DAS Storage |
| --------- | ---- | ----- | ----------- |
| Cubes XS  | 1    | 1 GB  | 30 GB       |
| Cubes S   | 1    | 2 GB  | 50 GB       |
| Cubes M   | 2    | 4 GB  | 80 GB       |
| Cubes L   | 4    | 8 GB  | 160 GB      |
| Cubes XL  | 6    | 16 GB | 320 GB      |
| Cubes XXL | 8    | 32 GB | 640 GB      |
| Cubes 3XL | 12   | 48 GB | 960 GB      |
| Cubes 4XL | 16   | 64 GB | 1280 GB     |

Cubes can boot from any storage volume, a CD-ROM, or a NIC.

This type of instance does not support "Live Vertical Scaling" (LVS) of CPU or RAM even if it is enabled on an image. It is not possible to migrate in higher or lower tiers of Cubes.

LVS is limited to NICs and block storage volumes. Please note that the number of direct attached NVMe storage volumes is limited to 1 (one) and it cannot be expanded, delete, removed from the Cubes instance or migrated to any other instance. Attaching further block storage volumes must be of type HDD or SSD. The scaling of resources without having to restart a virtual server can be applied as follows:

* Upscaling:NICs, HDD/ SSD storage volumes
* Downscaling: NICs, HDD/ SSD storage volumes

#### Additional Services

IONOS Cloud Cubes can be used inside a virtual data center in combination with any other service provided in this location.

#### Automatic Backup and Service Recovery

Every 24 hours, IONOS Cloud creates a backup of the direct attached NVMe volume automatically and stores it on a separate block storage device. In case of a host failure or outage, IONOS Cloud will recovery the Cubes instance from the backup. Since this backup is taken every 24 hours the user may want to apply additional backup or redundancy routines.

The automatic backup routine is included in IONOS Cloud Cubes and does not create additional costs.

#### Host Systems

IONOS Cloud is operates different types of host system based on AMD as well as Intel CPU architecture. All systems are configured to deliver same performance. A specific CPU type cannot be selected by the customer nor guaranteed by the IONOS Cloud.

### IONOS Cloud Block Storage

IONOS Cloud Hard Disk Drive (HDD) and Solid State Drive (SSD) Block Storage allow the customer to make use of a dual-redundant storage system. Each block storage created by the customer is stored on two storage servers, providing active-active redundancy. For additional data protection, every storage server is based either on a hardware RAID system or on a software RAID system.

For Direct Attached Storage (DAS) Block Storage based on Non-Volatile Memory Express (NVMe) are single-redundant storage systems. As this storage is installed directly into the physical server hosting the virtual machine, the storage volume is not stored across two servers. However, every DAS volume is covered by a software RAID system.

Access to the HDD and SSD volumes requested by the customer is achieved via the internal InfiniBand (RDMA) network. DAS volumes are connected to the mainboard of the server and benefit from fast peripheral component interconnect express (PCI express) bus performance.

For Solid State Drive volumes, IONOS Cloud offers two performance classes that can be selected at time of ordering the volume. SSD Premium is optimized for high performance while SSD Standard is recommended for fast data access with general-purpose scenarios.

HDD as well as DAS volumes deliver a static performance profile independent of the volume size. In comparison, SSD volumes deliver higher performance depending on the volume size and get capped at a specific size.

| Hard drive                     | Hard Disk Drive (HDD)                                                   |
| ------------------------------ | ----------------------------------------------------------------------- |
| Use                            | Shared                                                                  |
| Minimum and maximum size       | <p>1 GiB – 4 TiB per volume *</p><p>(up to 24 HDD per VM supported)</p> |
| Read / write speed, sequential | 200 MB/s at 1 MiB block size                                            |
| Read / write speed, random     | 1,100 IOPS at 4 KiB block size                                          |

_\*Larger volumes available on request._

| Hard drive                          | Solid State Drive (SSD) - Premium                                                      |
| ----------------------------------- | -------------------------------------------------------------------------------------- |
| Use                                 | Shared                                                                                 |
| Minimum and maximum size            | <p>1 GiB – 4 TiB per volume *<br>(up to 4 SSD per VM supported)</p>                    |
| Read / write speed, sequential      | 1 MB/s per GiB at 1 MiB block size                                                     |
| Max. read / write speed, sequential | <p>600 MB/s per VM at 1 MiB block size<br>and min. 4 Cores, 4 GB RAM per volume</p>    |
| Read speed, random                  | 75 IOPS per GiB at 4 KiB block size                                                    |
| Max. read speed, random             | <p>45,000 IOPS per VM at 4 KiB block size<br>and min. 4 Cores, 4 GB RAM per volume</p> |
| Write speed, random                 | 50 IOPS per GiB at 4 KiB block size                                                    |
| Max. write speed, random            | <p>30,000 IOPS per VM at 4 KiB block size<br>and min. 4 Cores, 4 GB RAM per volume</p> |

_\*Larger volumes available on request._

| Hard Drive                          | Solid State Drive (SSD) - Standard                                                     |
| ----------------------------------- | -------------------------------------------------------------------------------------- |
| Use                                 | Shared                                                                                 |
| Minimum and maximum size            | <p>1 GiB – 4 TiB per volume <em>*</em><br>(up to 24 SSD per VM supported)</p>          |
| Read / write speed, sequential      | 0.5 MB/s per GiB at 1 MiB block size                                                   |
| Max. read / write speed, sequential | <p>300 MB/s per VM at 1 MiB block size<br>and min. 2 Cores, 2 GB RAM per volume</p>    |
| Read speed, random                  | 40 IOPS per GiB at 4 KiB block size                                                    |
| Max. read speed, random             | <p>24,000 IOPS per VM at 4 KiB block size<br>and min. 2 Cores, 2 GB RAM per volume</p> |
| Write speed, random                 | 30 IOPS per GiB at 4 KiB block size                                                    |
| Max. write speed, random            | <p>18,000 IOPS per VM at 4 KiB block size<br>and min. 2 Cores, 2 GB RAM per volume</p> |

_\*Larger volumes available on request._

| Hard drive                     | Direct Attached Storage (DAS) NVMe                                      |
| ------------------------------ | ----------------------------------------------------------------------- |
| Use                            | Shared                                                                  |
| Minimum and maximum size       | <p>predefined per template 30 GiB - 640 GiB<br>(1 DAS per Cubes VM)</p> |
| Read / write speed, sequential | 250 MB/s at 1 MiB block size                                            |
| Read / write speed, random     | 5000 IOPS at 4 KiB block size                                           |
| Bandwidth per second burst     | <p>500 MB/s at 1 MiB block size</p><p>for 60 seconds</p>                |
| IOPS burst                     | <p>10000 IOPS at 4 KiB block size</p><p>for 60 seconds</p>              |

#### Snapshot

IONOS Cloud allows the customer to create so-called snapshots of individual block storages (HDD, SSD, DAS). A copy of each block storage can be accessed (and deleted) via DCD and Cloud API, and new block storages of any type can be created based on a snapshot. Provisioning speed is 50 MB/s.

#### Operating System Images

IONOS Cloud offers standardized images of the following operating systems:

* CentOS
* Debian
* Ubuntu
* Windows

New versions of the standardized images may be added and old versions will be removed when the vendor no longer supports them.

**Note:** We reserve the right to add non-LTS and testing/beta versions. Please follow the vendor's recommendations and refrain from using them for production use cases.

#### Image Upload

IONOS Cloud allows the customer to upload their own images to the infrastructure via upload servers. This procedure is to be completed individually for each data center location. IONOS Cloud optionally offers transmission with a secure transport (TLS). The uploading of HDD and CD-ROM/DVD-ROM images is supported. Specifically, the uploading of images in the following formats is supported:

**CD-ROM / DVD-ROM:**

* \*.iso ISO 9660 image file

**HDD Images:**

* \*.vmdk vmware HDD images
* \*.vhd, \*.vhdx HyperV HDD images
* \*.cow, \*.qcow, \*.qcow2 Qemu HDD images
* \*.raw binary HDD image
* \*.vpc VirtualPC HDD image
* \*.vdi VirtualBox HDD image

A dedicated upload server is available for each data center location. Images can be transmitted to the upload server encrypted via FTPS (FTP-TLS) or unencrypted via FTP.

The following upload servers are available:

* Berlin: ftp-txl.ionos.com
* Frankfurt: ftp-fra.ionos.com,
* Karlsruhe: ftp-fkb.ionos.com,
* Logroño: ftp-vit.ionos.com
* London: ftp-lhr.ionos.com
* Las Vegas: ftp-las.ionos.com,
* Newark: ftp-ewr.ionos.com.

Once the image has been transmitted to the upload server, the image will be converted into the internal image format of IONOS Cloud. The user will be informed by email when the conversion process starts.

Once the conversion is complete, the image will be available for use in the DCD or Cloud API under the name by which it was transmitted to the upload server.

#### Data Upload Service

IONOS Cloud offers customers the ability to transfer large amounts of data via a physically mailed data storage medium. This service supports a variety of data carrier interfaces like USB or SATA. To ensure data security, the data on the delivered data storage medium must be encrypted and have a total size of at least 1 TB.

All uploads are performed as a 1:1 copy to a volume and provided in the data center chosen by the customer. The customer is able to attach this volume to a virtual server of their choice in the chosen virtual data center.

After the upload is complete, the data storage medium will be returned to the customer. The data upload service can be requested by the 24/7 Enterprise Level Support.

#### Storage Availability Zones

In order to secure data, improve reliability and create high availability scenarios, customers can assign availability zones to HDD and SSD storage volumes (Storage Availability Zone for SSD in data center location Karlsruhe is not provided). DAS storage volumes do not support availability zones as they are installed to the physical compute servers directly. Virtual storage volumes, to which different storage availability zones are assigned operate on different physical resources. Availability zones can be assigned using the DCD or the Cloud API.

### Cloud-Init

IONOS Cloud offers Cloud-Init support for all of its Linux images. For Windows images, no Cloud-Init functionality is provided. The feature is activated in all locations. All public IONOS Cloud Linux images support Cloud-Init. For private images, it is the customer's responsibility to make sure that their own images support Cloud-Init.

At the moment, IONOS Cloud supports injection of user-data. Meta-data injection may be provided at a later point in time.

### Virtual Network

IONOS Cloud allows virtual entities to be equipped with network cards (“network interface cards”; NICs). Only by using these virtual network interface cards is it possible to connect multiple virtual entities together and / or to the Internet.

| Parameter                        | Size              | Performance |
| -------------------------------- | ----------------- | ----------- |
| Throughput, internal             | MTU 1,500         | 3 Gbps      |
| Throughput, external             | MTU 1,500         | 700 Mbps    |
| Maximum number of packets per VM | 100,000 packets/s |             |

_The maximum external throughput may only be achieved with a corresponding upstream of the provider._

**Compatibility**

* The use of virtual MAC addresses and/or the changing of the MAC address of a network adapter is not supported. Among others, this limitation also applies to the use of CARP (Common Address Redundancy Protocol).
* Gratuitous ARP (RFC 826) is supported.
* Virtual Router Redundancy Protocol (VRRP) is supported based on gratuitous ARP. For VRRP to work, IP failover groups must be configured.

### External Network

Depending on the location, different capacities for transmitting data to or from the Internet are available for operating the IONOS Cloud service. Due to the direct connection between the data centers at the German locations, the upstream can be used across locations.

The total capacity of each respective location is described below:

| Location               | Connection                           | Redundancy level | AS       |
| ---------------------- | ------------------------------------ | ---------------- | -------- |
| Berlin (DE)            | 2 x 100 Gbps                         | N+1              | AS-6724  |
| Frankfurt am Main (DE) | <p>2 x 100 Gbps<br>4 x 10 Gbps *</p> | N+5              | AS-51862 |
| Karlsruhe (DE)         | 3 x 10 Gbps2 \*\*                    | N+2              | AS-51862 |
| London (UK)            | 2 x 10 Gbps                          | N+1              | AS-8560  |
| Logroño (ES)           | 2 x 100 Gbps                         | N+1              | AS-8560  |
| Las Vegas (US)         | 3 x 10 Gbps                          | N+2              | AS-54548 |
| Newark (US)            | 2 x 10 Gbps                          | N+1              | AS-54548 |

_\* - 2 x 10 Gbps toward Karlsruhe; 2 x 10 Gbps toward the Internet_

_\*\* - 2 x 10 Gbps toward Frankfurt am Main; 1 x 10 Gbps toward the Internet_

IONOS backbone AS-8560, to which IONOS Cloud is redundantly connected, has a high quality edge capacity of 1.100 Gbps with 2.800 IPv4/IPv6 peering sessions, available in the following Internet and peering exchange points: AMS-IX, BW-IX,DE-CIX, ECIX, Equinix, FranceIX, KCIX, LINX.

### Internal Network

IONOS Cloud operates redundant networks at each location. All networks are operated using the latest components from brand manufacturers with connections up to 100 Gbps.

IONOS Cloud uses high-speed networks based on InfiniBand technology both for connecting the central storage systems and for handling internal data connections between customer servers.

### Core Network

IONOS Cloud operates a high availability core network at each location for the redundant connection of the product platform. All services provided by IONOS Cloud are connected to the Internet via this core network.

The core network consists exclusively of devices from brand manufacturers. The network connections are completed via an optical transmission network, which, by use of advanced technologies, can provide transmission capacities of several hundred gigabits per second. Connection to important Internet locations in Europe and America guarantee the customer an optimal connection at all times.

Data is not forwarded to third countries. At the customer’s explicit request, the customer can opt for support in a data center in a third country. In the interests of guaranteeing a suitable data protection level, this requires a separate agreement (within the meaning of article 44-50 DSGVO and §§ 78 ff. BDSG 2018).

### IP Address Management

IONOS Cloud provides the customer with public IP addresses that, depending on the intended use, can be booked either permanently or for the duration for which a virtual server exists. These IP addresses provided by IONOS Cloud are only needed if connections are to be established over the Internet. Internally, virtual machines can be freely networked. For this, IONOS Cloud offers a DHCP server that allows and/or simplifies the assignment of IP addresses. However, one can establish one’s own addressing scheme.

#### Public IPv4 Addresses

Every virtual network interface card that is connected to the Internet is automatically assigned a public IPv4 address by DHCP. This IPv4 address is dynamic, meaning it can change while the virtual server is operational or in the case of a restart.

Customers can reserve static public IPv4 addresses for a fee. These reserved IPv4 addresses can be assigned to a virtual network interface card, which is connected to the Internet, as primary or additional IP addresses.

#### Private IPv4 Addresses

In networks that are not connected to the Internet, each virtual network interface card is automatically assigned a private IPv4 address. This is assigned by the DHCP service. These IPv4 addresses are assigned statically to the MAC addresses of the virtual network interface cards.

The use of the IP address assignment can be enabled or disabled for each network interface card. Any private IPv4 addresses pursuant to RFC 1918 can be used in private networks.

| Network address range          | CIDR notation  | Abbreviated CIDR notation | Number of addresses        | Number of networks as per network class (historical)                                              |
| ------------------------------ | -------------- | ------------------------- | -------------------------- | ------------------------------------------------------------------------------------------------- |
| 10.0.0.0 to 10.255.255.255     | 10.0.0.0/8     | 10/8                      | <p>224 =<br>16.777.216</p> | <p>Class A:<br>1 private network with 16,777,216 addresses;<br>10.0.0.0/8</p>                     |
| 172.16.0.0 to 172.31.255.255   | 172.16.0.0/12  | 172.16/12                 | <p>220 =<br>1.048.576</p>  | <p>Class B:<br>16 private networks with 65,536 addresses;<br>172.16.0.0/16 to 172.31.0.0/16</p>   |
| 192.168.0.0 to 192.168.255.255 | 192.168.0.0/16 | 192.168/16                | <p>216 =<br>65.536</p>     | <p>Class C:<br>256 private networks with 256 addresses;<br>192.168.0.0/24 to 192.168.255.0/24</p> |

### Network Services

#### Cloud Connect

Cloud Connect enables the customer to create a direct and dedicated Layer-3 connection between their company network and their virtual data center (VDC). The customer can use Cloud Connect if both of the following conditions are fulfilled:

1. The connecting VDC is operated at the locations of Frankfurt, Berlin, or Las Vegas.
2. The customer has a dedicated line connection to the corresponding data center.

A connection can take place in different ways, for example, Dark-Fiber, MPLS or Cross Connect. For this purpose, the customer can contract a telecommunications company to establish the connection.

The 24/7 Enterprise Level Support is available to assist with any questions concerning the topic of Cloud exchange and connection.

#### IP-Failover

The IONOS Cloud IP-Failover feature helps to minimize packet loss for high availability or failover setups in the event that one of the virtual machines experiences an outage. By setting up IP-Failover groups for public traffic, customers can define the network interfaces of virtual servers that are part of a high availability setup.

“User” type accounts can create or edit IP-Failover groups using only reserved IP addresses, for which they have been granted access. The IP-Failover feature only provides provisioning of the same IP to multiple network interfaces from different virtual servers on the same LAN. It does not monitor the availability of the service to be accessed by the given IP. The monitoring and GARP announcements to gateways must be made by the customer individually on each virtual server that is a member of an IP-Failover setup.

#### Classic Load Balancing

IONOS Cloud offers the customer the function of a Classic Load Balancer for public traffic within their infrastructure. This load balancer distributes the incoming network traffic according to an ECMP algorithm on the servers configured behind the load balancer. The Classic Load Balancer is for basic balancing scenarios and does not provide granular configuration or health checks.

| Setting               | Value              |
| --------------------- | ------------------ |
| Throughput            | 50 Mbps            |
| Max. open connections | 40,000 connections |
| Max. backend servers  | 100                |

#### Firewall

IONOS Cloud allows the customer to use a software firewall within their infrastructure. For this purpose, the virtual network interface cards of a virtual server can be assigned a packet filter. The network traffic, which is aimed at the virtual server, is already filtered before the customer’s virtual machine.

| Setting                   | Value             |
| ------------------------- | ----------------- |
| Throughput                | 700 Mbps          |
| Maximum number of packets | 100,000 packets/s |

#### DHCP

For every network interface of a virtual server, IONOS Cloud provides an IP configuration via DHCP. In this context, the type of the configuration distinguishes between whether the network interface is connected with the public Internet or a private Ethernet.

**Public Internet:**

The following parameters are provided for the configuration via DHCP:

* Public IPv4 address
* Network mask (255.255.255.255)
* Gateway address
* DNS server address
* MTU (1,500)

**Private Networks:**

The following parameters are provided for the configuration via DHCP:

* Private IP address (10.x.x.x)
* Network mask (255.255.255.0)
* MTU (1,500)

The DHCP server always uses the address A.B.C.1 in the class C network, which corresponds to the assigned IP address.

The configuration through DHCP can be optionally activated or deactivated via network interface (DCD, or Cloud API). The configuration via DHCP is activated for newly created network interfaces.

#### DNS

**Caching DNS**

For the resolution of public domain names, IONOS Cloud operates a redundant set consisting of two DNS servers at every data center location.

These DNS servers are operated as “caching” DNS servers and / or DNS resolvers, and are automatically assigned to the virtual customer entities via the DHCP IP address resolution.

Customer-specific internal domains cannot be resolved on caching DNS servers.

**Reverse DNS**

A standard reverse entry is assigned to all public IP addresses, which are assigned to the virtual entities.

These entries follow the format pAAA-BBB-CCC-DDD.pbiaas.com, whereby AAA-BBB-CCC-DDD corresponds to the IPv4 octets.

For statically assigned IP addresses, the existing reverse entry can be adapted according to the customer requirements via a Service Request to the 24/7 Enterprise Level Support.

#### IONOS DDoS Protect

IONOS DDoS Protect is a managed Distributed Denial of Service defense mechanism, which ensures that every customer resource hosted on IONOS Cloud is secure and resilient against Layer 3 and Layer 4 DDoS attacks. This is facilitated by a filtering and scrubbing technology, which in event detection of an attack filters the malicious DDoS traffic and lets through only the genuine traffic to its original destination. Hence, enabling applications and services of our customers to remain available under a DDoS attack.

Known attack vectors regularly evolve and new attack methods are added. IONOS Cloud monitors this evolution and dedicates resources to adapt and enhance DDoS Protect as much as possible to capture and mitigate the threat.

The service is currently available in the following data centers: Berlin, Frankfurt, and Karlsruhe, and will be available in the remaining data centers soon.

\
The service is available is two packages:

**DDoS Protect Basic:** This package is enabled by default for all customers and does not require any configuration. It provides basic DDoS Protection for every resource on IONOS Cloud from common volumetric and protocol attacks and has the following features:

* DDoS traffic filtering - All suspicious traffic is redirected to the filtering platform where the DDoS traffic is filtered and the genuine traffic is allowed to the original destination.
* Always-On attack detection - The service is always on by default for all customers and does not require any added configuration or subscription.
* Automatic Containment - Each time an attack is identified the system automatically triggers the containment of the DDoS attack by activating the DDoS traffic and letting through only genuine traffic.
* Protection against common Layer 3 and 4 attacks - This service protects every resource on IONOS Cloud from common volumetric and protocol attacks in the Network and Transport Layer such as UDP, SYN floods, etc.

**DDoS Protect Advanced:** This package offers everything that is part of the DDoS Protect Basic package plus advanced security measures and support.

* 24/7 DDoS Expert Support - Customers have 24/7 access to IONOS Cloud DDoS expert support. The team is available to assist customers with their concerns regarding ongoing DDoS attacks or any related issues.
* Proactive Support - The IONOS Cloud DDoS support team, equipped with alarms, will proactively respond on a DDoS attack directed towards a customer's resources and also notify the customer in such an event.
* On-demand IP specific DDoS filtering - If a customer suspects or anticipates a DDoS attack at any point in time, they can request to enable DDoS filtering for a specific IP or server owned by them. Once enabled, all traffic directed to that IP will be redirected to the IONOS Cloud filtering platform where DDoS traffic will be filtered and genuine traffic will be passed to the original destination.
* On-demand Attack Diagnosis - At the customer's request, a detailed report of a DDoS attack is sent to the customer, explaining the attack and other relevant details.

NOTE: IONOS Cloud sets forth Security as a Shared Responsibility between IONOS Cloud and the customer. We at IONOS Cloud strive at offering a state-of-the-art DDoS defense mechanism. Successful DDoS defense can only be achieved by a collective effort on all aspects including optimal use of firewalls and other settings in the customer environment.

#### Flow Logs

Flow logs is a feature that allows you to capture data related to IPv4 network traffic flows. Flow logs can be enabled for any network interface of a virtual machine (VM) instance and Network Load Balancer, as well as the public interfaces of the Network Address Translation\*\* (\*\*NAT) Gateway.

Flow logs can help you with a number of tasks such as:

* Debugging connectivity and security issues
* Monitoring network throughput and performance
* Logging data to ensure that firewall rules are working as expected

The service can be configured for the direction of network traffic (ingress, egress, bi-directional) as well as action (accepted, rejected traffic packets or any). Data is collected by the services and submitted in a compressed file to a customer's IONOS Cloud S3 bucket, which can be specified by the customer at time of flow log activation.

The service will not update existing files but will send new flow log records in a new compressed in an interval of 10 minutes.

## IONOS Cloud Managed Services

### IONOS Cloud Managed Kubernetes

IONOS Cloud Managed Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications. It groups containers that make up an application into logical units for easy management and discovery. Container technology makes software development more flexible and agile, however it is quite complex to manage and requires a certain level of expertise.

IONOS Cloud Managed Kubernetes facilitates the fully automated setup of Kubernetes clusters. Several clusters can also be quickly and easily deployed, for example to set up staging environments, and then deleted again if necessary. Kubernetes also significantly simplifies the automation of CI/CD pipelines in terms of testing and deployment.

IONOS Cloud Managed Kubernetes solution offers maximum transparency and control of the K8s cluster. This includes:

* Fully automated setup of entire K8s clusters and K8s node pools (with optional horizontal auto-scaling of nodes)
* Highly-available and geo-redundant control plane
* Full cluster admin-level access to Kubernetes API
* Dedicated CPU and memory resource assignment
* Double redundant and persistent HDD/SSD storage
* Easy integration of Cloud services
* Regular security and version updates

IONOS Cloud Managed Kubernetes is free of charge. The customer pays only for the underlying IONOS Cloud infrastructure that is actually needed.

### Managed Network Load Balancer

IONOS Cloud offers a Managed Network Load Balancer (NLB) that is balancing layer 4/ TCP-based network traffic. This service is available in all locations. A Managed Application Load Balancer (ALB) for layer 7/ http(s) based network traffic will be provided soon.

Network Load Balancers can be provisioned as private as well as public load balancers. A public load balancers requires the configuration of a reserved public IP address for the target configuration. The network load balancer allows configuration of multiple, individual load balancer rules which can be applied to virtual machines being member of the listener LAN.

The Network Load Balancers supports multiple load balancing algorithms.

* Round Robin
* Least Connection
* Random
* Source IP

Furthermore, it offers options to specify health parameters to include or exclude nodes from the balancing configuration as well as manually remove listener targets from the load balancer (e.g. when the node is in maintenance).

The number of Managed Network Load Balancers per contract is limited to five (5) NLBs per contract. This limit can be adjusted by contacting the IONOS Cloud Support Team.

Currently, the Managed Network Load Balancer is in Early Access phase. It operates in a modus that recovers the service within a few minutes. At the end of the Early Access phase the Managed Network Load Balancer will be operated in high-availability modus and service recovery is executed within seconds.

### Managed NAT Gateway

In all location, IONOS Cloud provides a Managed Network Address Translation (NAT) Gateway. This service is exposing a Source NAT gateway which means it allows access from the virtual instance to the internet but blocks requests from the internet to the virtual infrastructure. This enables internet access to virtual machines without exposing them to the internet by a public interface. While being "hidden" from the internet and being not exposed to threats the virtual machine still can initiate a connection to the customizable targets in the internet e.g. to download new software updates or patches.

A Managed NAT Gateway requires the configuration of a reserved public IP address for the target configuration. The Managed NAT Gateway allows configuration of multiple, individual NAT rules which can be applied to virtual machines being member of the listener LAN individually. These rules allow dedicated configuration of target subnets as well as port ranges which are explicitly allowed to be accessed by virtual machine instances.

The Managed NAT Gateway supports TCP, UDP and ICMP protocols and up to six private networks per NAT Gateway. The number of Managed NAT Gateways per contract is limited to five (5) gateways per contract. This limit can be adjusted by contacting the IONOS Cloud Support Team.

Currently, the Managed NAT Gateway is in Early Access phase. It operates in a modus that recovers the service within a few minutes. At the end of the Early Access phase the Managed NAT Gateway will be operated in high-availability modus and service recovery is executed within seconds.

## IONOS Cloud S3 Object Storage

IONOS Cloud S3 Object Storage is a standalone object storage solution based on the S3 API (Simple Storage Services) standard. IONOS Cloud provides facilities to manage and maintain accessibility to the object storage. The user can access object storage either through a browser application, or through any standard S3 client or library of their choice.

IONOS Cloud S3 Object Storage offers the industry’s best compatibility with the S3 API, which guarantees a high level of interoperability and compatibility with other object storage systems adhering to S3. Apart from the standard operations, which S3 entails, it allows a multitude of additional operations, such as:

* Versioning
* Logging
* Object encryption
* Detailed access management by means of access control lists (ACLs)
* Deleting multiple objects automatically
* Hosting a static website
* Cross Region Replication
* Object Lock

IONOS Cloud S3 Object Storage is available for every contract and does not require further registration or activation. By means of a graphical interface as well as other standard S3 clients, customers can manage their objects and define access to them applying ACLs (access control lists) as defined by the S3 standard.

Our object storage is currently available in the following locations (further locations will follow).

| Location       | S3 API Endpoint                                                              | Static Website                                                                                |
| -------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Frankfurt (DE) | <p>s3-eu-central-1.ionoscloud.com</p><p>*.s3-eu-central-1.ionoscloud.com</p> | <p>s3-website-de-central.profitbricks.com</p><p>.s3-website-de-central.profitbricks.com *</p> |
| Berlin (DE)    | <p>s3-eu-central-2.ionoscloud.com</p><p>*.s3-eu-central-2.ionoscloud.com</p> | <p>s3-website-eu-central-2.ionoscloud.com</p><p>*.s3-website-eu-central-2.ionoscloud.com</p>  |
| Logroño (ES)   | <p>s3-eu-south-2.ionoscloud.com</p><p>*.s3-eu-south-2.ionoscloud.com</p>     | <p>s3-website-eu-south-2.ionoscloud.com</p><p>*.s3-website-eu-south-2.ionoscloud.com</p>      |

\* - The hostname of static website for location Frankfurt points to a S3 installation from ProfitBricks which was the legal predecessor of IONOS Cloud.

## IONOS Cloud Backup

IONOS Cloud is implementing the backup solution in partnership with the backup pioneer and market leader, Acronis. A theoretically unlimited volume of data can be stored in data centers, guaranteed and fully certified to ISO 27001. Data cables with capacities of up to 10 GBit/s ensure seamless data throughput, even for full backups.

Features of the fully integrated backup function:

* Comprehensive image backup (full backup) and/or incremental backup
* Rapid disaster recovery and complete data restore
* Easy data migration
* Encrypted data storage in ISO-certified data centers in Germany

IONOS Cloud Backup allows the customer to perform a quick and efficient backup of data from applications and any images the customer is using. The customer can also backup data from applications that run on-premises or in private Clouds in commonly used virtualized environments such as VMware and Hyper-V.

The fully integrated backup system supports following platforms:

* Windows Server and Desktop operating systems
* Linux
* Mac
* Hyper-V and other Hypervisor solutions
* Workstations, physical and virtual servers

## IONOS Private Cloud powered by VMware

IONOS Private Cloud powered by VMware brings VMware enterprise-class Software-Defined Data Center software to the IONOS Cloud portfolio, enabling customers to run any application across vSphere-based private Cloud environments.

The Service Offering has the following components:

* Private Cloud consisting of:
  * VMware vSphere Enterprise Plus running on dedicated servers
  * VMware vCenter Server appliance
  * VMware NSX-T Standard to power networking for the Service Offering
  * VMware vSAN Standard aggregating host-based storage into a shared data store
* Self-service provisioning and scaling of Private Cloud on demand
* Access to the vSphere Client and NSX-T Manager, ability to configure and design the virtual data center that best fits to ones use cases
* Maintenance, patching, and upgrades of the PC (the hardware, physical infrastructure and VMware stack), performed by IONOS

IONOS Private Cloud powered by VMware can be provisioned and scaled vertically on demand. A Private Cloud cluster includes a minimum of three hosts. Customers can add hosts, up to the provisioning maximum for their organization (maximum 24 hosts per cluster). Customers can select the location of the data center where their Private Cloud will be provisioned. Currently, the service is available in Berlin (Germany), Gloucester (UK) and Logroño (Spain). The location of Karlsruhe Baden AirPark will continue to operate already provisioned instances but does not allow provisioning of new private cloud setups.

IONOS Private Cloud powered by VMware runs exclusively on high performance, state-of-the-art hardware and virtualization technology. vSAN, NSX-T, Intel Optane and NVMe storage provide processing speeds that significantly optimize your workloads.

## 24/7 Enterprise Level Support

IONOS Cloud offers its customers technical support by telephone and email. Experienced system administrators take the customers’ calls and emails and address their concerns immediately. 24/7 Enterprise Level Support can be contacted by email or telephone 24 hours a day, seven days a week, via the following contact details:

[https://dcd.ionos.com/help/en/contact.htm](https://dcd.ionos.com/help/en/contact.htm)

## Data Centers

IONOS Cloud uses data centers at different locations worldwide. The security concepts of the data centers are always based on the highest industry standards.

### IONOS Cloud Compute Engine Locations

#### Berlin (Germany)

| Property                  | Details                                                                       |
| ------------------------- | ----------------------------------------------------------------------------- |
| Operator                  | United Internet AG                                                            |
| Certifications            | ISO/IEC 27001                                                                 |
| Fire protection zones     | One                                                                           |
| Power supply              | Availability 99.99% p. a.                                                     |
| Battery buffer            | Yes                                                                           |
| Emergency power           | A/B system, 2N USV redundancy, Emergency diesel generator with N+1 redundancy |
| Air conditioning          | Cold aisle containment, blow-in temperature 23 °C                             |
| Early fire detection      | Yes                                                                           |
| Fire extinguishing system | Yes                                                                           |

#### Frankfurt am Main (Germany)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | Equinix (Germany) GmbH                                                                               |
| Certifications            | ISO/IEC 27001, ISO 9001, SSAE 16/ISAE 3402, (SOC1, SOC2), PCI-DSS                                    |
| Fire protection zones     | Three                                                                                                |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | Cold aisle containment, blow-in temperature 22 °C                                                    |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

#### Karlsruhe (Germany)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | TelemaxX Telekommunikation GmbH                                                                      |
| Certifications            | ISO/IEC 27001                                                                                        |
| Fire protection zones     | Two                                                                                                  |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | <p>No explicit containment,<br>temperature within data center 23 °C</p>                              |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

_Since 21st April 2020, it is no longer possible to create new virtual data centers in Karlsruhe._

#### London (UK)

| Property                  | Details                                                                                                            |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Operator                  | Virtus Data Centres Ltd.                                                                                           |
| Certifications            | ISO/IEC 27001, ISO 9001, ISO 14001, ISO 50001, ISO 20000, ISAE 3402 compliant, PCI-DSS compliant, BREEAM excellent |
| Fire protection zones     | One                                                                                                                |
| Power supply              | Availability 99.99% p. a.                                                                                          |
| Battery buffer            | No – the generators are rotary                                                                                     |
| Emergency power           | <p>Emergency diesel generator with N+2 redundancy,<br>capable of being refueled during operation</p>               |
| Air conditioning          | <p>Hot aisle containment,<br>temperature within data center 23 °C</p>                                              |
| Early fire detection      | Yes                                                                                                                |
| Fire extinguishing system | Yes                                                                                                                |

#### Logroño (ES)

| Property                  | Details                                                                                                                         |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Operator                  | Arsys Internet S.L.U.                                                                                                           |
| Certifications            | AENOR ecommerce, ISO/IEC 27001, ISO 9001, ISO 50001, ENS Conformity, Uptime Tier III, SAP Certified in Cloud and Infrastructure |
| Fire protection zones     | Nine                                                                                                                            |
| Power supply              | Availability 99.98s% p. a.                                                                                                      |
| Battery buffer            | Yes                                                                                                                             |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p>                            |
| Air conditioning          | <p>Hot aisle containment,<br>temperature within data center 23 °C</p>                                                           |
| Early fire detection      | Yes                                                                                                                             |
| Fire extinguishing system | Yes                                                                                                                             |

#### Las Vegas (USA)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | Switch, Inc.                                                                                         |
| Certifications            | ISO/IEC 27001, ISO 9001, SSAE 16/ISAE 3402 (SOC1, SOC2), PCI-DSS                                     |
| Fire protection zones     | Two                                                                                                  |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+2 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | <p>Hot aisle containment,<br>temperature within data center 22 °C</p>                                |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

#### Newark (USA)

| Property                  | Details                                                                                    |
| ------------------------- | ------------------------------------------------------------------------------------------ |
| Operator                  | QTS Realty Trus, Inc.                                                                      |
| Certifications            | SOC1, SOC2, PCI, ISO27001, HITRUST                                                         |
| Fire protection zones     | One                                                                                        |
| Power supply              | Availability 99,99+% p. a.                                                                 |
| Battery buffer            | No – the generators are rotary                                                             |
| Emergency power           | Emergency diesel generator with N+2 redundancy, capable of being refueled during operation |
| Air conditioning          | <p>Cold aisle,<br>temperature within data center approximately 23 °C</p>                   |
| Early fire detection      | Yes                                                                                        |
| Fire extinguishing system | Yes                                                                                        |

### IONOS Private Cloud powered by VMware Locations

#### Karlsruhe - Baden AirPark (Germany)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | 1&1 IONOS SE                                                                                         |
| Certifications            | ISO/IEC 27001, ISO/IEC 50001                                                                         |
| Fire protection zones     | Three                                                                                                |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | Cold aisle containment, blow-in temperature 22 °C                                                    |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

_Since 05th July 2021, it is no longer possible to create new Private Cloud servers in Baden AirPark._

#### Berlin (Germany)

| Property                  | Details                                                                       |
| ------------------------- | ----------------------------------------------------------------------------- |
| Operator                  | United Internet AG                                                            |
| Certifications            | ISO/IEC 27001, IT Grundschutzt                                                |
| Fire protection zones     | One                                                                           |
| Power supply              | Availability 99.99+% p. a.                                                    |
| Battery buffer            | Yes                                                                           |
| Emergency power           | A/B system, 2N USV redundancy, Emergency diesel generator with N+1 redundancy |
| Air conditioning          | Cold aisle containment, blow-in temperature 23 °C                             |
| Early fire detection      | Yes                                                                           |
| Fire extinguishing system | Yes                                                                           |

#### Logroño (Spain)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | Arsys Internet S.L.U. (100% subsidiary of 1&1 IONOS SE)                                              |
| Certifications            | ISO/IEC 27001, ISO/IEC 50001                                                                         |
| Fire protection zones     | Two                                                                                                  |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | Cold aisle containment, blow-in temperature 22 °C                                                    |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

#### Gloucester (UK)

| Property                  | Details                                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| Operator                  | Fasthosts Internet Ltd. (100% subsidiary of 1&1 IONOS SE)                                            |
| Certifications            | ISO/IEC 27001, ISO/IEC 50001, PCI-DSS                                                                |
| Fire protection zones     | One                                                                                                  |
| Power supply              | Availability 99.99+% p. a.                                                                           |
| Battery buffer            | Yes                                                                                                  |
| Emergency power           | <p>Emergency diesel generator with N+1 redundancy,<br>capable of being refueled during operation</p> |
| Air conditioning          | <p>No explicit containment,<br>temperature within data center 23 °C</p>                              |
| Early fire detection      | Yes                                                                                                  |
| Fire extinguishing system | Yes                                                                                                  |

## Document Version

Status: 2021-11
