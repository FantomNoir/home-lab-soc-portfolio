# Lab 4 — TCP Three-Way Handshake Investigation

## Objective
Inspect a TCP three-way handshake in Wireshark, verify relative sequence and acknowledgment numbers, and recognize subsequent TLS negotiation.

## Environment
- Apple MacBook M2 running macOS
- Wireshark capture on interface `en0`
- Test connection: `https://example.com`
- TCP destination port: `443` (HTTPS)
- TCP stream: `19`

## Investigation summary
The client initiated a connection from ephemeral port `51301` to TCP port `443`. The server replied with SYN-ACK, and the client completed the handshake with ACK. A TLS 1.3 Client Hello with SNI `example.com` followed at frame 1026.

### Packet evidence

| Frame | Observed TCP flags | Relative sequence | Relative acknowledgment |
|---|---|---:|---:|
| 1023 | SYN, ECE, CWR | 0 | Not valid (ACK not set) |
| 1024 | SYN, ACK, ECE | 0 | 1 |
| 1025 | ACK | 1 | 1 |

The initial packet's TCP flag field was `0x0c2`, indicating SYN, ECE, and CWR set. This is consistent with ECN capability negotiation.

## Timing
- SYN: `50.605780` seconds
- SYN-ACK: `50.621783` seconds
- Final ACK: `50.622015` seconds
- Observed SYN-to-SYN-ACK interval: approximately **16.003 ms**, not a complete end-to-end performance measurement.

## Security assessment
The reviewed traffic shows a successful TCP handshake and subsequent TLS 1.3 negotiation. The reviewed packets do not independently establish malicious activity.

## SOC analyst relevance
- TCP packet analysis and protocol troubleshooting
- TCP flag interpretation, including ECN-related flags
- Sequence and acknowledgment number verification
- TLS negotiation recognition
- Evidence-based investigation reporting

## Supporting screenshots
Two locally prepared, sanitized Wireshark screenshots are available in the Lab 4 evidence package, but **have not yet been uploaded to this repository**. Their local filenames are:
- `01_tcp_handshake_sanitized.png`
- `02_tcp_flags_sanitized.png`

Raw packet captures have not been published. Verify that screenshots do not reveal personal or network identifiers before uploading them to this public repository.
