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


# problems you might run into setting up GNS3

You might see this: <br/> 

**3) Virtualized Intel VT-x/EPT is not supported on this platform. Continue without virtualized Intel VT-x/EPT?
**
<img width="324" height="151" alt="not supported" src="https://github.com/user-attachments/assets/92980ddd-2a99-4683-8cb1-7fce2a7282d7" />

Click yes it might not run or Click No (lets fix this)

## Resolve it p1

- Open control panel
- Click on Programs
- Click on Programs and Features
- Turn on windows feature on or off

<img width="590" height="188" alt="control pannel pt-1" src="https://github.com/user-attachments/assets/36730b25-ceb8-4316-8246-778fe595089e" />

- Uncheck Virtual Machine Platform
- Uncheck Windows Hypervisor Platform

Before you restart your machine

<img width="701" height="260" alt="powershell" src="https://github.com/user-attachments/assets/d6b75bbb-c847-4ead-b3cd-0eb80e694df8" />
<br/>
<img width="730" height="188" alt="turn off auto hyper-v launc" src="https://github.com/user-attachments/assets/1038ec79-eda9-4fc6-8ce3-2814b86dd01d" />

- Run powershell as Administrator (right click on powershell)
- type this command bcdedit /set hypervisorlaunchtype off   
- This command disables the Hyper-V hypervisor from launching automatically when Windows boots.

Restart your machine and run GNS3 again if problem not solved follow steps bellow ⬇️⬇️

## Resolve it p2
