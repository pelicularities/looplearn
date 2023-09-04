- **OSI:** Open Systems Interconnection
- **Networking stack:** the software that handles each of the layers of the OSI model

## Media layers
### Layer 1: Physical
- Transmission of data over some shared physical medium:
	- Copper
	- Fiber
	- Radio frequencies (wi-fi)
- Specifications define transmission/reception of **raw bit streams** between transmitter and receiver
	- i.e. how are `1`s and `0`s represented in this physical medium?
	- voltage levels
	- timing
	- data rates
	- etc.
#### Hubs
- Receives data on any port
- Retransmits data to all other ports
	- Including errors
	- Including collisions

#### Mental model for Layer 1
- One [broadcast domain](https://en.wikipedia.org/wiki/Broadcast_domain): only broadcast possible
- One [collision domain](https://en.wikipedia.org/wiki/Collision_domain)
- **No device addressing:** can't send data to a specific device over layer 1
- **No media access control (MAC):** no way to restrict transmission to specific devices
- **No collision detection:** can't guarantee that transmissions will only occur when no other transmissions are happening

### Layer 2: Data Link
#### MAC address
- **Hardware** address, not software assigned
- 48 bits
- OUI: organisationally unique identifier (24 bits assigned to a manufacturer)
#### Ethernet frames
Each frame consists of:
- Preamble: identifies start of frame
- MAC header:
	- Destination MAC address
		- `ff:ff:ff:ff:ff:ff` for broadcast
	- Source MAC address
	- EtherType (which Layer 3 protocol generated this frame?)
- Payload
- Frame Check Sequence (FCS)
	- [CRC](https://en.wikipedia.org/wiki/Cyclic_redundancy_check) checksum
	- Check for errors in data transmission

#### Carrier Sense Multiple Access / Collision Detection (CSMA / CD)
- Wikipedia: [Carrier-sense multiple access with collision detection](https://en.wikipedia.org/wiki/Carrier-sense_multiple_access_with_collision_detection)
- Sender checks at layer 2: does it recognise the destination?
- If yes: sends the frame directly to destination
- If no: passes the frame to layer 1, converted to physical data standard
- Destination receives the data, converts to frame
	- Is it the intended destination?
		- If yes: processes payload
		- If no: discards payload
- If existing transmission is detected: further transmissions are deferred to avoid collision
- If collision is detected: jam signal, retry after random time interval
#### Switches
- Stores and forwards frames received on its ports
- Associates a MAC with a port using frames
- No longer needs to transmit on every port if it knows which port the destination is on
- **Each port is a separate collision domain**

#### Types of Layer 2 protocols
- [Ethernet](https://en.wikipedia.org/wiki/Ethernet)
- [IEEE 802.11 wireless LAN](https://en.wikipedia.org/wiki/IEEE_802.11)
- [Point-to-Point Protocol (PPP)](https://en.wikipedia.org/wiki/Point-to-Point_Protocol)

#### Mental model for Layer 2
- **Device addressing is possible:** can send data to a specific device over Layer 2
	- Corollary: **unicast** is possible
- **Media access control (MAC):** transmission from specific devices can be restricted and managed
- **Collision detection:** can detect and correct collisions
### Layer 3: Network

## Host layers
### Layer 4: Transport
### Layer 5: Session
### Layer 6: Presentation
### Layer 7: Application
- Web browsers
- Web servers