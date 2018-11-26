# IFT220_Lab4

### This lab is about policies, Group Policies and Fain Grained Password Policies.

#### Deliverable

#### Overview:
1. Create a GPO to configuring time synchronization for all computers in the domain.
1. Create a GPO to configure default password policy for users in the domain.
1. Create a FGPP to force Privileged Users (Users with administrator access) to have longer passwords than normal users.


**Time Synchronization**
As you read in Chapter 2, "Active Directory is highly dependent on all of the domain controllers and domain members having synchronized clocks." Desmond, B., Richards, J., Allen, R., & Lowe-Norris, A. G. (2013). Active Directory (Fifth). O’Reilly Media. 
1. In generial, we're following this https://www.altaro.com/hyper-v/configuring-time-synchronization-for-all-computers-in-windows-domain/
    1. If you are running virtualbox, here's how to disable time sync on your VM https://superuser.com/questions/984040/how-to-disable-time-sync-with-windows-7-as-host-os-in-virtualbox/984041
  
**Default Password Policy**
1. Create a GPO in your domain, and link it our domain.
    1. Configure the Account Policies/Password Policy as followes:
      1. Maximum password age                         90 days 
      1. Minimum password age                         10 days 
      1. Minimum password length                      10 characters
      1. Password must meet complexity requirements   Enabled 
      1. Store passwords using reversible encryption  Disabled 

