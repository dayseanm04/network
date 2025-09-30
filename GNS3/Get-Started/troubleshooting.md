# Problems you might run into setting up GNS3

You might see this: <br/> 

**1) VMware Workstation does not support nested virtualization on this host.**    <br/>
**Module 'HV' power on falled.**    <br/>
**Failed to start the virtual machine.**    <br/>


<img width="628" height="340" alt="failed to start vm" src="https://github.com/user-attachments/assets/35fd8064-e99f-4045-af69-90fe21f86fc1" />

- This might be becuase You have other hypervisors on your machine
- I have enabled Hyper-v on my machine
- So I will disbale Hyper-V


## Resolve it

<img width="704" height="208" alt="control panel step-1" src="https://github.com/user-attachments/assets/84918f29-31ec-4322-81cf-908c66814c20" />

- Open Control Pannel
- Click on Programs
- Click on Programs and Features
- Click on Turn on Windows features on or off

<img width="401" height="359" alt="control panel step-2" src="https://github.com/user-attachments/assets/44cc0bbb-6abb-4091-84ca-db906b2c0633" />


- Uncheck Hyper-V
- Click OK
- Then restart your machine


You might also see this: <br/> 

**2) You are running this virtual machine with side channel
mitigations enabled. Side channel mitigations provide
enhanced security but also lower performance.**

**To disable mitigations, change the side channel
mitigations setting in the advanced panel of the
virtual machine settings...**

<img width="344" height="238" alt="side channel" src="https://github.com/user-attachments/assets/d4a91537-379e-4e31-9479-29895281f229" />

Click on OK (We are going to disable it)

## Resolve it

First turn off GNS3 vm if its on

Right click on the vm in VMware <br/>
<img width="414" height="430" alt="vm settings" src="https://github.com/user-attachments/assets/2694221f-cd15-43ed-846c-6ff0e05dcf06" />


- Click on settings
- Click on Advanced
- Check Disable side channel mitigations for Hyper-V enabled hosts

<img width="616" height="269" alt="disable side channel" src="https://github.com/user-attachments/assets/38a715a3-eeb0-4864-b056-cd9ced5c2f71" />

Click on OK
