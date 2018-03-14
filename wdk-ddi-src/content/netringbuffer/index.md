---
UID: NA:netringbuffer
ms.assetid: 99647C91-F445-4970-9398-C7CCC97E2703
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netringbuffer.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netringbuffer.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetRingBufferGetElementAtIndex function](nf-netringbuffer-netringbuffergetelementatindex.md) | Returns the element at the specified index in the ring buffer. |
| [NetRingBufferGetNumberOfElementsInRange function](nf-netringbuffer-netringbuffergetnumberofelementsinrange.md) | Calculates the number of elements contained in a range of the specified net ring buffer. |
| [NetRingBufferIncrementIndex function](nf-netringbuffer-netringbufferincrementindex.md) | Returns the next index value after the specified index value, wrapping around to the beginning of the ring buffer if necessary. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_RING_BUFFER structure](ns-netringbuffer-_net_ring_buffer.md) | Specifies a buffer comprised of one or more NET_PACKET structures. | 