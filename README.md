NEO Mesh Suggested Node Configurations

These settings are only a suggestion -- but certain settings are explicitly required to be able to communicate with the rest of the mesh.

We're only listing settings we have suggestions for, this list is not comprehensive.

# All Nodes

## Radio Configuration
### LoRa

| Setting | Value | Notes |
|---------|-------|-------|
|Region   | US
|Use Preset | On
|Preset | LongFast | Required to participate in the mesh
|OK to MQTT | On
|Number of Hops | 7 

## Channels

| # | Name | Key | Notes |
|---|------|-----|-------|
| 0 | (Default) | `AQ==` | Leave at defaults, enable position if you want

Set the rest of the channels however you like.

## Security
Always back up your keys.  Set everything else to your preferences.

## Device Configuration
### User
Configure how you like.  Leave "licensed operator off" even if you're a ham.

### Bluetooth
For devices without a display, we strongly recommend changing the bluetooth PIN.

## Module Configuration

### MQTT
#### What is MQTT and why does it matter?

In a standard Meshtastic mesh, nodes communicate with each other over LoRa radio — messages hop from node to node until they reach their destination. This works great locally, but is limited by range and the number of hops a message can take.

MQTT extends the mesh over the internet. When a node with internet access (via WiFi or a paired phone) receives a LoRa message, it can forward ("uplink") that message to an MQTT broker — a central server that other nodes also connect to. Those remote nodes can then receive the message and rebroadcast it over their local LoRa radio ("downlink"), effectively bridging geographically distant mesh networks together.

For NEO Mesh, this means a node in one part of Northeast Ohio can exchange messages with a node in a completely different area that would otherwise be out of radio range — as long as both have internet-connected nodes nearby that are linked to `mqtt.neomesh.org`.

A few things to keep in mind:

- **"OK to MQTT"** (set in LoRa config above) must be enabled for your messages to be forwarded to the broker. If it's off, internet-connected nodes will not uplink your messages even if they receive them.
- **Client Proxy** means your node uses a paired phone's internet connection to reach the broker, rather than its own WiFi. Use this if your node doesn't have WiFi.
- **Encryption Enabled** ensures messages are not sent to the broker in plaintext.
- MQTT participation is optional — nodes without internet access still participate fully in the local LoRa mesh.
 
If you'd like to participate in NEO Mesh MQTT server:

| Setting | Value | Notes |
|---------|-------|-------|
| Enabled | On
| Client Proxy | (See notes) | Off if device is connected to wifi, otherwise on
| Encryption Enabled | On
| Root Topic | `msh/US/OH`
| Server Address | `mqtt.neomesh.org`
| Username | `neomesh`
| Password | `meshneo`
| TLS Enabled | Off


# Client/Companion Nodes
Everyday nodes you carry with you

## Device Configuration
### Device
| Setting | Value | Notes |
|---------|-------|-------|
| Role | Client Mute | Client can be fine in some situations

# House/Low-Profile Permanent Nodes

## Radio Configuration
### Security
Add the public keys from your client node(s) to enable remote admin.

## Device Configuration
### Device
| Setting | Value | Notes |
|---------|-------|-------|
| Role | Client Base | Make sure to add your companion nodes as favorites

## Module Configuration
### Telemetry
| Setting | Value | Notes |
|---------|-------|-------|
| Broadcast Device Metrics | On | Helps keep track of battery level, air utilitzation, etc.


# High-Profile Nodes

## Radio Configuration
### Security
Add the public keys from your client node(s) to enable remote admin.

## Device Configuration
### Device
| Setting | Value | Notes |
|---------|-------|-------|
| Role | Router | Coordinate with the community on Discord.

## Module Configuration
### Telemetry
| Setting | Value | Notes |
|---------|-------|-------|
| Broadcast Device Metrics | On | Helps keep track of battery level, air utilitzation, etc.


