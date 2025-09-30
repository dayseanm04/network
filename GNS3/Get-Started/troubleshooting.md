# problems you might run into setting up GNS3

You might see this: <br/> 

**VMware Workstation does not support nested
virtualization on this host.
Module HV power on falled.
Failed to start the virtual machine.**


<img width="628" height="340" alt="failed to start vm" src="https://github.com/user-attachments/assets/35fd8064-e99f-4045-af69-90fe21f86fc1" />

- This might be becuase You have other hyper visors on your machine
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
