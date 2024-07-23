---
layout: post
title: Datagrams
tags: computer-networks
---

Imagine sending a message in a bottle across the ocean. Each bottle has a short message, your friend's address, and a number to tell them which order to read the messages in case they get more than one. That's like a datagram on the Internet.

## Formal Explanation

A **datagram** is a basic unit of data transfer in a packet-switched network. It is a self-contained, independent packet that carries information necessary for its delivery. Datagrams are used in communication protocols where reliability and ordering are not guaranteed, such as the User Datagram Protocol (UDP).

### Characteristics of a Datagram

1. **Self-contained**: Each datagram contains all the information needed for it to be delivered to its destination, including source and destination addresses.
2. **Independent**: Datagrams are sent independently of each other and can take different paths to reach their destination.
3. **Connectionless**: Datagram-based communication does not require establishing a connection between sender and receiver before data is transmitted.
4. **Unreliable**: There is no guarantee that datagrams will arrive in the order sent or even arrive at all. There is no built-in mechanism for error checking and correction.
5. **Best-effort delivery**: The network will do its best to deliver datagrams, but there is no guarantee of delivery, order, or duplicate protection.

### How Datagrams Work

1. **Creation**: A datagram is created by the sender with all necessary information, including the payload (data being sent), source address, and destination address.
2. **Transmission**: The datagram is sent over the network. It may be broken into smaller packets if the payload is too large.
3. **Routing**: Each datagram is independently routed through the network. Routers determine the best path for each datagram to take.
4. **Delivery**: The datagram arrives at the destination, where it is reassembled if necessary. The application processes the data without any guarantee of order or reliability.

## Example of Datagram Use

**User Datagram Protocol (UDP)**:
   - UDP uses datagrams for communication. It is commonly used in applications where speed is critical, and some data loss is acceptable, such as video streaming, online gaming, and VoIP (Voice over Internet Protocol).

## Advantages of Datagrams

1. **Speed**: Since datagrams do not require a connection to be established, they can be sent quickly, making them ideal for real-time applications.
2. **Simplicity**: The protocol for sending datagrams is simpler than connection-oriented protocols, which reduces overhead.
3. **Efficiency**: Datagrams are suitable for broadcasting and multicasting, where the same data needs to be sent to multiple receivers.

## Disadvantages of Datagrams

1. **Unreliable Delivery**: There is no guarantee that datagrams will reach their destination or that they will arrive in order.
2. **No Error Correction**: Datagrams do not have built-in mechanisms for error detection and correction, so applications need to handle these issues if required.

## References

- [User Datagram Protocol (UDP)](https://en.wikipedia.org/wiki/User_Datagram_Protocol)
- [Internet Protocol (IP) Datagram](https://www.ibm.com/docs/en/i/7.4?topic=SSAW57_7.4/com.ibm.iyig.doc/c_ipv4datagram.htm)
- [How Datagram Networks Work](https://www.geeksforgeeks.org/difference-between-datagram-packet-virtual-circuit/)

