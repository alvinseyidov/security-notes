## Packet Analysis and Traffic Inspection

Packet analysis reveals how systems truly communicate.
Logs summarize activity, but packets show exact behavior.

Every attack, misconfiguration, and anomaly appears
at the packet level.

---

## What a Network Packet Contains

### Headers
Control information used for delivery:
- MAC addresses
- IP addresses
- Ports
- Flags and sequence numbers

### Payload
The actual data being transmitted.

### Metadata
Timing, packet size, interface details.

---

## Packet Structure by Layer

- Ethernet (Layer 2): MAC addressing
- IP (Layer 3): Network routing
- TCP / UDP (Layer 4): Transport
- Application (Layer 7): HTTP, DNS, TLS

Packet order:
Ethernet → IP → TCP/UDP → Application data

---

## Packet Capture Tools

### Wireshark
- GUI-based analysis
- Deep protocol inspection
- Best for learning and investigation

### tcpdump
- Command-line capture
- Lightweight and fast
- Ideal for servers

### Tshark
- CLI Wireshark
- Automation and scripting

---

## Packet Sniffing Methods

### Promiscuous Mode
- Captures packets visible to the interface
- Limited on switched networks

### Monitor Mode (Wi-Fi)
- Captures raw wireless frames
- Listens to radio traffic directly

### Port Mirroring (SPAN)
- Switch copies traffic to monitoring port
- Required for full visibility in wired networks

---

## Traffic Analysis Concepts

### Sessions
Full connection lifecycle.

### Streams
Reconstructed application data.

### Conversations
Communication patterns between endpoints.

---

## Identifying Protocols in Traffic

- Port numbers
- Header patterns
- Handshake behavior
- Payload structure

Encrypted traffic still exposes:
- IPs
- Ports
- Timing
- TLS handshake metadata

---

## Detecting Anomalies

Common indicators:
- Unusual ports
- High-volume bursts
- Frequent small packets
- Unexpected destinations
- Repeated failed connections
- Long-lived sessions

---

## Encryption and Visibility

### Visible
- Source and destination IPs
- Ports
- Packet size and timing
- TLS handshake details

### Hidden
- Application content
- Credentials
- Commands and responses

Patterns often reveal threats even when content is encrypted.

---

## Legal and Ethical Considerations

- Capture traffic only with authorization
- Respect privacy and scope
- Secure stored packet captures
- Follow organizational policies

---

## Why This Matters

Packet analysis enables:
- Incident investigation
- Threat detection
- Network troubleshooting
- Validation of security controls
