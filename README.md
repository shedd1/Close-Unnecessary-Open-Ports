# Close-Unnecessary-Open-Ports
Unnecessary open ports provide potential entry points for an attacker. Ports 80, 443, and 3306 are open, although there is no intention of ACIDM01 hosting a website. In this case, these ports should be closed
## Device ##
- ACIDM01 - Windows Server 2022 - Domain Member Server
- Windows Defender Firewall

## Let's Start ##
- Connect to ACIDM01
- Click the Start charm and type the following:
    - Windows defender firewall
    - Select Windows Defender Firewall with Advanced Security
- In Windows Defender with Advanced Security, select Inbound Rules on the left pane
    - Select New Rule in the Actions pane.
- In the New Inbound Rule Wizard - Rule Type page, select the radio button next to Port
    - Click Next
- In the Protocol and Ports page, type the following in the Specific local ports field:
    - 80, 443, 3306
    - Click Next
- In the Profile page, ensure the Domain, Private, and Public options are ticked
    - Click Next
- In the Name page, type the following in the Name field:
    - Close unnecessary ports
    - Click Finish
- Observe the rule at the top of the Inbound Rules list, which has been created to block ports 80, 443, and 3306
    - Close the Windows Defender with Advanced Security window
- Connect to ACIKALI, where the Terminal Emulator window is open
    - Type the following and press Enter:
    - nmap -Pn 192.168.0.2
<img width="566" height="109" alt="image" src="https://github.com/user-attachments/assets/59c5b1c8-3bab-4431-bcae-8713f80b6b38" />

- ### Notice that ports 80, 443, and 3306 are no longer listed as open ports. They have been closed by the Windows Defender Firewall Rule that was created ###
