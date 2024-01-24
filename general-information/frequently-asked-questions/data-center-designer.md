# Data Center Designer

### How do I connect to a server using the DCD?

Each server has a Remote Console that can be accessed using the DCD. This Remote Console is available in two versions, which is used depending on your browser:

* Java Applet
* HTML5

We recommend using the **HTML5** version.

### How do I manage user permissions?

In the **DCD**, go to **Menu** > **Management** > **Users & Groups**. The **User Manager** will open up. It allows contract owners and administrators to organize users. From the User Manager, the administrator can provide users with permissions and access to the resources of an IONOS account.

### What is the difference between a shutdown and a power stop?

When a Virtual Machine (VM) is shut down only at the operating system level, the hardware resources it consumes remain allocated to the VM, and the costs for these resources continue to be charged. To avoid unnecessary costs, use the DCD to stop the VM and deallocate its resources. Costs for CPU cores and RAM will then no longer apply. Associated storage, however, is not deallocated automatically when the VM is stopped and will continue to be charged until deleted manually.

### How can I fix the error message "Missing required Permissions manifest attribute in main jar"?

Add an exception for the [<mark style="color:blue;">https://dcd.ionos.com</mark>](https://dcd.ionos.com) URL to resolve this error in your browser's Java configuration.

### Why are there no switch elements?

DCD does not use switches for creating network segments because functions such as switching, routing, and forwarding are deeply integrated into the IONOS Software Defined Network (SDN) stack. The traffic distribution is handled by IONOS.

### How is provisioning conducted?

Provisioning allocates billable resources required to start operating your VDC. Provisioning means that the infrastructure of your virtual data center is made available for use. Once all the changes to your VDC have been completed, you can begin the provisioning process. Please note that this process cannot be undone.

An existing data center can be modified at any time. Note that the provisioning process cannot be undone. Your password will be requested to edit some of the elements as an additional security measure.

Before starting provisioning, you will be alerted about any issues or errors and can review all changes. As an additional security measure for critical changes, you may have to enter your password before provisioning can begin.

DCD verifies changes in the following ways before provisioning: 
* Validation
* Delta 

### Are there provisioning validation safeguards?

DCD ensures a smooth provisioning process by checking the validity of new VDC configurations. This is done before provisioning and while creating VDCs.

* **Live validation:** Live validation identifies errors that would block the provisioning process and provides assistance with their immediate resolution. Errors and warnings that do not stop the provisioning process or messages requesting a password confirmation are not displayed.

* **Dialog box:** The new configuration is checked for errors before starting the provisioning process. For example, you receive notifications if default element names are unchanged. The built-in help function will assist you in resolving such errors.

Select the **Delta** tab in the **Provision Data Center** to review all changes before starting the provisioning process. A categorized list of changes is displayed as follows:

* Added
* Deleted
* Updated

The authorization in DCD is based on the creation of roles and groups. Users inherit permissions and access rights granted to the group or groups of which they are members.

### How are user roles assigned?

Permissions are associated with roles and groups. Roles define what users are allowed to do and to which part of the DCD they have access. The following roles can be attributed:

| Contract Owners                                                                                                                          | Administrators                                                                                                                                                   | Users |
| ------------------------------------------------------------------------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------ |
| All users who register with IONOS Cloud are automatically the contract owners.          | Administrators have the same permissions as contract owners. However, they cannot change the payment method.                       | A user is any member who has been added to the contract by the contract owner.  |
| Only contract owners have access to the **User Manager**. They can view the resource and cost overview and change the payment method of the contract. They can add or remove users from your contract, create groups, and grant permissions and access rights.  | Administrators can assign administrator rights to other users.                  |  After a user has been assigned to a group, they have, at a minimum, read access to the resources assigned to the group. Permissions are required for some activities in the DCD. |
| Only contract owners have access to the **User Manager**. They can view the resource and cost overview and change the payment method of the contract. They can add or remove users from your contract, create groups, and grant permissions and access rights.  | Administrators do not need to be managed in groups, as they automatically have access to all resources associated with the contract.     | 
| The contract can grant users, in their contract, administrator rights by activating the respective checkboxes in the **User Manager**.        | The administrator can grant users, in their contract, administrator rights by activating the respective checkboxes in the **User Manager**.                                      |

### How are user groups divided?

The groups facility allows a contract owner or an administrator to:

* Define what users are allowed to do in the DCD.
* Define which resources (VDC, images, snapshots, IP blocks) they have access to.

Administrators do not need to be managed in groups. They automatically have access to all resources associated with the contract. There is no limit to the number of groups and users that can be created.
