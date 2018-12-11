# IFT220_Lab4

## This lab is about Group Policies and Fine-Grained Password Policies.

### Deliverable
* The deliverable for the lab is the completed "IFT220 Lab4 Worksheet" from this repo


### Overview
1. Create a GPO to configuring time synchronization for all computers in the domain.
1. Create a GPO to configure default password policy for users in the domain.
1. Create a FGPP to force Privileged Users (Users with administrator access) to have longer passwords than normal users.
 
 
**Time Synchronization**
* As you read in Chapter 2, "Active Directory is highly dependent on all of the domain controllers and domain members having synchronized clocks" (Desmond, B., Richards, J., Allen, R., & Lowe-Norris, A. G. (2013). *Active Directory* (Fifth). O’Reilly Media.).
1. We're following the "Configuring the Windows Time service to use an external time source" section at https://support.microsoft.com/en-us/help/816042/how-to-configure-an-authoritative-time-server-in-windows-server and using this list of peers `0.pool.ntp.org,0x1 1.pool.ntp.org,0x1 2.pool.ntp.org,0x1 3.pool.ntp.org,0x1` in step 4.
    1. If you are running VirtualBox, here's how to disable time sync on your VM https://superuser.com/questions/984040/how-to-disable-time-sync-with-windows-7-as-host-os-in-virtualbox/984041


**Default Password Policy**
1. Create a GPO in your domain and link it to your domain.  Configure the Account Policies/Password Policy as follows:

    Policy | Setting
    ------------------------------------------- | -------
    Maximum password age | 90 days
    Minimum password age | 10 days
    Minimum password length | 10 characters
    Password must meet complexity requirements | Enabled
    Store passwords using reversible encryption | Disabled


**Fine-Grained Password Policy**
* Sparky Technologies is concerned about security and knows that if an administrator account is hacked it will be a nightmare, so they want to make all **Privileged Account** holders have stronger (longer) passwords then normal users.  
* The Information Security Officer found https://blogs.technet.microsoft.com/canitpro/2013/05/29/step-by-step-enabling-and-using-fine-grained-password-policies-in-ad online and wants you, the AD Lead, to implement it on the domain with a **minimum password of 17 characters** and a **maximum password age of 30 days**.
* She knows it should be applied to the IT group, but wants to know if there are other Privileged Accounts outside of the IT group.

