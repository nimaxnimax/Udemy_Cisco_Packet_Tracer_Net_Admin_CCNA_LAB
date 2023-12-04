Chapter 4 Lab

Default Username and Password: cisco

****************************************************************************************************
1: IP Address Configuration & Verification >> Router

To configure IP addresses on Cisco router interfaces, you need to access the router's command-line interface (CLI) and use the following commands. Assuming you want to configure IP address 192.168.11.254/24 on FastEthernet0/0 (fa0/0) and 192.168.13.254/24 on FastEthernet0/1 (fa0/1), here are the steps:

1. Access the router's CLI using a terminal emulator like PuTTY, Tera Term, or HyperTerminal.

2. Enter privileged exec mode by typing:

    ```bash
    enable
    ```

3. Enter global configuration mode:

    ```bash
    configure terminal
    ```

4. Navigate to the interface configuration mode for FastEthernet0/0:

    ```bash
    interface FastEthernet0/0
    ```

5. Assign the IP address and subnet mask to FastEthernet0/0:

    ```bash
    ip address 192.168.11.254 255.255.255.0
    ```

   If you are using a /24 subnet mask, you can also use the following shorthand:

    ```bash
    ip address 192.168.11.254 255.255.255.0
    ```

6. Enable the interface:

    ```bash
    no shutdown
    ```

   This command ensures that the interface is up and operational.

7. Repeat the process for FastEthernet0/1:

    ```bash
    interface FastEthernet0/1
    ip address 192.168.13.254 255.255.255.0
    no shutdown
    ```

8. Exit interface configuration mode:

    ```bash
    exit
    ```

9. Save the configuration to the startup configuration file to ensure that the changes persist after a reboot:

    ```bash
    write memory
    ```

Your configuration should look like this:

```bash
interface FastEthernet0/0
 ip address 192.168.11.254 255.255.255.0
 no shutdown

interface FastEthernet0/1
 ip address 192.168.13.254 255.255.255.0
 no shutdown
```

This configuration assumes that the router has FastEthernet interfaces labeled as fa0/0 and fa0/1. Adjust the interface labels based on your specific router model and configuration. Additionally, ensure that the specified IP addresses and subnet masks match your network requirements.


****************************************************************************************************
2: Configuring Gateway for Clients >> PCs and Notebooks

For Windows clients in the network with the IP range 192.168.11.0/24, set the default gateway to 192.168.11.254 in the IP configuration. Similarly, for clients in the network with the IP range 192.168.13.0/24, set the default gateway to 192.168.13.254 in the IP configuration.


****************************************************************************************************
3: Telnet Configuration Example >> Router

To configure Telnet on a Cisco router with the password "cisco" and an exec timeout of 30 minutes, you can use the following commands. These commands should be entered in the router's command-line interface (CLI):

1. Access the router's CLI using a terminal emulator like PuTTY, Tera Term, or HyperTerminal.

2. Enter privileged exec mode by typing:

    ```bash
    enable
    ```

3. Enter global configuration mode:

    ```bash
    configure terminal
    ```

4. Set the Telnet password:

    ```bash
    line vty 0 4
    password cisco
    login
    ```

   This command configures the Telnet password as "cisco" and requires password authentication for Telnet access.

5. Set the exec timeout to 30 minutes:

    ```bash
    line vty 0 4
    exec-timeout 30 0
    ```

   This command sets the exec timeout to 30 minutes. The values "30 0" represent 30 minutes and 0 seconds.

6. Exit global configuration mode:

    ```bash
    exit
    ```

7. Save the configuration to the startup configuration file to ensure that the changes persist after a reboot:

    ```bash
    write memory
    ```

Your configuration should look like this:

```bash
line vty 0 4
 password cisco
 login
 exec-timeout 30 0
```

This configuration assumes that you are configuring the Telnet parameters for the virtual terminal lines (vty) 0 to 4. Adjust the line numbers if needed based on your specific requirements.

Please note that using a simple password like "cisco" is not recommended for production environments. In a real-world scenario, it is advisable to use a strong, complex password for security reasons.

