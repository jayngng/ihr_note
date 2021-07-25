# Scenario

When it comes to responding to an incident on enterprise environments, time to respond and visibility are everything.

There will be incidents, when waiting until an IR team is deployed or remotely logging into each under-investigation endpoint and issuing numerous commands, won't be the optimum response approach.

---

Suppose that, multiple incidents have been declared inside a heterogeneous enterprise network and you are called to dig deeper and identify what is actually happening.

Luckily, the corporation has deployed [GRR](https://github.com/google/grr) clients on its endpoints and subsequently, you will be able to have both a bird's eye view of the network and on-demand access to crucial endpoint information.

The list of affected endpoints (which also happen to feature a GRR client) is:

-   _win10-server.els-child.eLS.local_
    
-   _jumpbox.els-child.eLS.local_
    
-   _xubuntu_

# Recommended tools

-   [GRR](https://github.com/google/grr)
    
-   [xxd](http://manpages.ubuntu.com/manpages/trusty/man1/xxd.1.html) (Linux-based tool)
    
<hr>

# Network Configuration & Credentials

-   Incident Responder's Subnet: **172.16.66.0/24**
    
-   Under-investigation endpoints' subnet: **10.100.11.0/24**
    
-   GRR server
    
    -   **IP**: 10.100.11.122
-   Connection Type: **VNC**
    
    -   Use a Linux or Windows VNC client (https://www.tightvnc.com/download.php) to connect to GRR-Server (10.100.11.122)

```
vncviewer 10.100.11.122 <- For Linux-based machines
tvnviewer.exe, Remote Host:10.100.11.122 <- For Windows-based machines
```

A static route has been configured, so that the Incident Responder can interact with the endpoints on the 10.100.11.0/24 subnet.]

To log into the GRR administration panel (after you connect to the GRR > server through VNC as mentioned above):

1.  Open a web browser
    
2.  Navigate to **localhost:8000**
    
3.  Submit the following credentials: **admin**/**@nalyst**