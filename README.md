*This project has been created as part of the 42 curriculum by ainradan.*

# NetPractice

## Description

NetPractice is a practical introduction to the basics of **computer networking**. The goal of the project is to make small-scale, simulated networks work properly by fixing their configuration.

For each of the 10 training levels, a non-functioning network diagram is displayed in a web interface, along with one or more objectives (for example: *host A must be able to communicate with host C*). The task is to adjust the editable fields (IP addresses, subnet masks, routing tables, default gateways) until every goal is reached.

Through the 10 levels, the project covers:

- Configuring valid **IP addresses** for hosts and router interfaces.
- Choosing correct **subnet masks** so that devices share (or do not share) the same network.
- Understanding the role of a **router** and of a **default gateway**.
- Building and reading **routing tables** (destination => next hop).
- Reading the interface logs to understand why a packet is dropped (invalid IP, missing gateway, no matching route, etc.).

> The networks used in this project are simulated and fictitious. They are not connected to real-world configurations.

## Instructions

### Running the training interface

1. Download the archive attached to the project's page and extract it into any folder.
2. In that folder, run the launcher script:

   ```sh
   ./run.sh
   ```

   This starts a local web server and opens your default web browser on the NetPractice page.
   Then open `http://localhost:49242` in your web browser.

### Using the interface

1. Enter your **intranet login** (`ainradan`) in the field of the *Training* tab so that your personal configuration is generated. (The *Evaluation* tab generates a random configuration, suitable for evaluations.)
2. Modify the **unshaded fields** of the diagram (IP, mask, routes).
3. Click **[Check again]** to verify your configuration. The logs at the bottom of the page explain why a goal fails.
4. Once the level is successful, click **[Get my config]** to export the configuration file of the level.
5. Click **[Next level]** to move on to the following level.

> Do not forget to export the configuration with **Get my config** *before* moving to the next level.

### Submission requirements

- There are **10 levels**, so **10 exported configuration files** (one per level) must be submitted.
- These 10 files must be placed at the **root of the Git repository**, together with this `README.md`.
- The login must be entered in the interface before exporting, otherwise the exported files will not be valid.
- Only the content of the repository is evaluated during the defense.
- During the defense, three random levels must be completed within a limited amount of time. No external tools are allowed (a simple calculator such as `bc` is tolerated, but it is the limit).

### Repository layout

```
.
├── README.md
├── <level 1 configuration file>
├── <level 2 configuration file>
├── ...
└── <level 10 configuration file>
```

## Resources

### Networking concepts studied

- **TCP/IP addressing**: IPv4 addresses, network address, broadcast address, host range, private vs. public ranges.
- **Subnet masks**: dotted-decimal notation and CIDR notation (e.g. `255.255.255.0` = `/24`), subnetting, computing the number of usable hosts.
- **Default gateways**: the router address used by a host to reach networks outside its own subnet.
- **Routers and switches**: routers connect different networks and forward packets according to a routing table; switches connect devices inside the same network.
- **Routing tables**: destination network, next hop, and the default route `0.0.0.0/0`.
- **OSI layers**: the seven-layer model, with a focus on layer 2 (data link, switches) and layer 3 (network, IP and routers).

### References

- [RFC 791 – Internet Protocol](https://datatracker.ietf.org/doc/html/rfc791)
- [RFC 1918 – Address Allocation for Private Internets](https://datatracker.ietf.org/doc/html/rfc1918)
- [RFC 4632 – Classless Inter-domain Routing (CIDR)](https://datatracker.ietf.org/doc/html/rfc4632)
- [Wikipedia – IPv4](https://en.wikipedia.org/wiki/IPv4)
- [Wikipedia – Subnetwork](https://en.wikipedia.org/wiki/Subnetwork)
- [Wikipedia – Default gateway](https://en.wikipedia.org/wiki/Default_gateway)
- [Wikipedia – OSI model](https://en.wikipedia.org/wiki/OSI_model)
- [Cloudflare Learning – What is a subnet?](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/)

### Use of AI

AI tools were used as a learning aid only, never to solve the levels in my place:

- **Concept explanation**: clarifying notions such as subnet masks, CIDR notation, default gateways and routing tables.
- **Checking understanding**: reviewing my own reasoning about address ranges and routes, then verifying the results in the training interface and with peers.
