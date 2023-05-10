# reliable-transfer-protocols
An implementation of the Alternating Bit, Go Back N, and Selective Repeat Protocols in C++.

Access to view code is available upon request, this is to maintain compliance with University at Buffalo's Academic Integrity Policy.

Example of Go Back N and Selective Repeat Protocols: https://tinyurl.com/2ztum37d

The protocols are run on a simulated network provided by UB's course staff for CSE489 Modern Networking Concepts.

### Alternating Bit Protocol
- A reliable data transfer protocol that sends 1 packet at a time, sequence numbers alternate between 1 and 0.
- Only 1 packet is allowed to be transferred at a time, another packet may not be transferred until the current packet is acked.
- Consists of a basic timer that on timeout prompts the retransmission of the current packet.

### Go Back N Protocol
- A reliable data transfer protocol that allows multiple packets to be sent at the same time.
- Uses a window to limit the number of packets able to transmit at one time.
- Sequence numbers increment so that every packet has a unique sequence number.
- Consists of a simple timer for the entire window, when the timer runs out, the entire window is retransmitted.
- The window is shifted once the packet at the base of the window is acked.

### Selective Repeat Protocol
- A reliable data transfer protocol that allows multiple packet to be sent at the same time independently of each other.
- Uses a window to limit the number of packets able to transmit at one time.
- Sequence numbers increment so that every packet has a unique sequence number.
- Consists of a simulated multiple timer setup(1 physical timer), one timer per packet, when a timer runs out, the packet associated with that timer is retransmitted.
- The window is shifted once the packet at the base of the window is acked.

All protocols ensure in order delivery of data to the application layer.
