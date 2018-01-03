## Entry Analysis

### filter.c

* ​
* line 1170 `FilterSendNetBufferListsComplete`
* ==line 1248 `FilterSendNetBufferLists`==
* ==line 1433 `FilterReceiveNetBufferLists`==
  * modify the NBL chain
  * modify a Netbuffer packet
  * queue the NBLs in a local structure

### device.c

* line 135, `ndislwfmixDeviceIoControl`
* ​

### Helper functions

* NdisFreeNetBuffer, NdisFreeNetBufferList
* ​

## Device Control IOCTL

p

## Net Buffer List Mapping

p

## IP Helper Function

p





Filter driver do not provide direct support for legacy send and receive operations that are based on the NDIS_PACKET structure.

Instead, NDIS converts receive indications from legacy miniport drivers to NET_BUFFER structures.

Also, NDIS handles the  required conversions from send requests that are based on NET_BUFFER structures to legacy send requests that are based on NDIS_PACKET stuctures.



Filtr drivers call the NdisFSendNetBufferLists function to send the network data that is defined in a list of NET_BUFFER_LIST structures.