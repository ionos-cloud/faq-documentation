# Data Center Designer

### Q: How do I connect to a server using the DCD?

Each server comes with a Remote Console that can be accessed using the DCD. This Remote Console is available in two versions, with the one used depending on your browser:

* Java applet
* HTML5

We recommend using the HTML5 version.

### Q: How do I manage user permissions?

The User Manager allows Contract Owners and Administrators to organize Users. From the User Manager, the Administrator can provide Users with permissions, and access to the resources of an IONOS account.

### Q: What is the difference between a shutdown and a power stop?

When a VM is shut down only at the operating system level, the hardware resources it consumes remain allocated to the VM, and the costs for these resources continue to be charged. To avoid unnecessary costs, use the DCD to stop the VM and deallocate its resources. Costs for CPU cores and RAM will then no longer apply. Associated storage, however, is not deallocated automatically when the VM is stopped and will continue to be charged until deleted manually.

### Q: How can I fix the error message "Missing required Permissions manifest attribute in main jar"?

To resolve this error, add an exception for the URL [https://dcd.ionos.com](https://dcd.ionos.com) in your browser's Java configuration.

### Q: Why are there no switch elements?

DCD does not use switches for creating network segments, because functions such as switching, routing, and forwarding are deeply integrated into the IONOS Software Defined Network (SDN) stack. The traffic distribution is handled by IONOS.

### Q: How does IONOS Cloud provision resources?

Provisioning allocates billable resources required to start operating your VDC. "Provisioning" means that the infrastructure of your virtual data center is made available for use. Once all the changes to your VDC have been completed, you can begin the provisioning process. Please note that this process cannot be undone.

An existing data center can be modified at any time. Please note that the provisioning process cannot be undone. Your password will be requested for editing some of the elements as an additional security measure.

Prior to the start of provisioning, you will be alerted about any issues or errors and can review a h2 of all changes. As an additional security measure for critical changes, you may have to enter your password before provisioning can begin.

DCD verifies changes in several ways before provisioning: 1) **Validation** and the 2) **Delta view.**

### Q: How is validation conduction prior to provisioning?

DCD ensures a smooth provisioning process by checking the validity of new VDC configurations. This is done prior to provisioning (provisioning dialog box) and while creating VDCs (live validation).

**Live validation:** Live validation identifies errors that would block the provisioning process and provides assistance with their immediate resolution. Errors and warnings that do not block the provisioning process, or messages requesting a password confirmation, are not displayed.

**Dialog box:** Prior to starting the provisioning process, the new configuration is checked for errors. For example, you receive notifications if default element names are unchanged. The built-in help function will assist you in resolving such errors.

To review all changes prior to starting the provisioning process, select the Delta tab in the Provision Data Center dialog box. A categorized list of changes is displayed as follows:

* Added
* Deleted
* Updated

The authorization philosophy in DCD is based on the creation of roles and groups. Users inherit permissions and access rights granted to the group or groups of which they are members.

### Q: How are roles assigned inside of the DCD?

Permissions are associated with roles and groups. Roles define what users are allowed to do and to which part of the DCD they have access. The following roles can be attributed:

All users who register with IONOS Cloud are automatically the Contract Owner.Only Contract Owners have access to the User Manager. They can view the resource and cost overview and change the payment method of the contract.They can add or remove users from your contract, create groups, and grant permissions and access rights.The Contract Owner or an Administrator can grant users, in their contract, Administrator rights by activating the respective checkboxes in the User Manager.Administrators have the same permissions as Contract Owners. However, they cannot change the payment method.Administrators can assign administrator rights to other users.Administrators do not need to be managed in groups as they automatically have access to all resources associated with the contract.A User is any member who has been added to the contract by the Contract Owner. After a User has been assigned to a group, they have at a minimum, read access to the resources assigned to the group.Permissions are required for some activities in the DCD.

The following table provides an overview of the available roles and their permissions:

with appropriate authorization by an Administrator or Contract Holder

### Q: How are user groups divided?

The Groups facility allows a Contract Owner or an Administrator to:

* Define what Users are allowed to do in the DCD.
* Define which resources (VDC, images, snapshots, IP blocks) they have access.

Administrators do not need to be managed in groups. They automatically have access to all resources associated with the contract.

There is no limit to the number of Groups and Users that can be created.
