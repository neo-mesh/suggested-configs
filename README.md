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


