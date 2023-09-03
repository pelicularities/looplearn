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
#### Mental model for Layer 1
- One [broadcast domain](https://en.wikipedia.org/wiki/Broadcast_domain)
- One [collision domain](https://en.wikipedia.org/wiki/Collision_domain)
- **No device addressing:** can't send data to a specific device over layer 1
- **No collision detection:** can't guarantee that transmissions will only occur when no other transmissions are happening
- **No media access control (MAC):** no way to restrict transmission to specific devices
#### Hubs
- Receives data on any port
- Retransmits data to all other ports
	- Including errors
	- Including collisions

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
	- CRC checksum
	- Check for errors in data transmission

### Layer 3: Network

## Host layers
### Layer 4: Transport
### Layer 5: Session
### Layer 6: Presentation
### Layer 7: Application
- Web browsers
- Web servers