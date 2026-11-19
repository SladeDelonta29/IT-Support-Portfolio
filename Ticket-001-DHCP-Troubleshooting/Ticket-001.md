# Ticket #001: DHCP Address Assignment Failure — APIPA Troubleshooting

**Environment:** SysDesks IT Support Simulation  
**Category:** Network Troubleshooting / DHCP  
**Status:** Resolved

### 1. Issue
Jordan Reyes, an employee in the Sales department, reported losing network connectivity after reconnecting his laptop to a docking station following a meeting.

Websites failed to load with DNS-related errors, and email services were unavailable. Windows displayed **"Unidentified Network — No Internet Access"**, despite detecting a wired Ethernet connection.

The employee had already disconnected and reconnected the Ethernet cable without success and needed connectivity restored before an upcoming client call.

<img width="1060" height="360" alt="Screenshot 2026-11-19 031618" src="https://github.com/user-attachments/assets/3c42aa8f-595a-45fc-aa19-7180d0f3f332" />


### 2. Investigation
I remotely accessed the employee's computer and opened Command Prompt to investigate the network configuration.

I executed the following command:

`ipconfig /all`

The results showed an IPv4 address beginning with **169.254.x.x**, indicating that Windows had assigned an Automatic Private IP Addressing (APIPA) address.

This suggested that the computer had been unable to obtain a valid IPv4 configuration from the DHCP server.
<img width="901" height="509" alt="Ticket#1 issue" src="https://github.com/user-attachments/assets/3c514333-4a97-4389-91a0-46ea1fad8f6b" />



### 3. Root Cause
The computer had failed to obtain a usable IPv4 address through DHCP and was operating with an APIPA address.

This prevented normal network connectivity. Although the employee experienced DNS-related errors, the underlying issue was consistent with a DHCP address assignment failure.

The specific reason the initial DHCP request failed was not established.

### 4. Resolution
I used Command Prompt to release the existing network configuration:

`ipconfig /release`

After releasing the configuration, the IPv4 address displayed as `0.0.0.0`.

I then requested a new DHCP configuration using:

`ipconfig /renew`

The computer successfully obtained the private IPv4 address **10.20.14.88**, with a subnet mask of **255.255.255.0**.

### 5. Verification
I ran `ipconfig /all` again and confirmed that the computer had obtained a new IPv4 address.

I also checked network connectivity and confirmed that it was working.

After completing the troubleshooting process, I notified Jordan that connectivity had been restored and asked him to check his connection. I then closed the simulated support ticket.
<img width="1579" height="899" alt="Ticket#1 solution" src="https://github.com/user-attachments/assets/7837a9d0-3a82-43c6-a5d8-8a3f26300d6f" />



### 6. Key Takeaway
This troubleshooting exercise reinforced the importance of examining IP configuration when diagnosing network connectivity problems.

An IPv4 address beginning with `169.254` can indicate that Windows was unable to obtain an address through DHCP.

Using `ipconfig /release` and `ipconfig /renew` can help restore DHCP configuration when the network and DHCP service are available.

The exercise also highlighted the importance of verifying connectivity, communicating with the user, and documenting the troubleshooting process before closing a support ticket.
