---
UID: NS:1394._IRB_RECEIVE_PHY_PACKETS
title: "_IRB_RECEIVE_PHY_PACKETS"
author: windows-driver-content
description: This structure contains the fields necessary to carry out a ReceivePhyPackets request.
old-location: ieee\irb_req_receive_phy_packets.htm
old-project: IEEE
ms.assetid: FE160EB4-EDBD-4783-A02D-F82D2842ADD0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_IRB_RECEIVE_PHY_PACKETS, IEEE.irb_req_receive_phy_packets, IRB_REQ_RECEIVE_PHY_PACKETS structure [Buses], IRB_REQ_RECEIVE_PHY_PACKETS, 1394/IRB_REQ_RECEIVE_PHY_PACKETS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_RECEIVE_PHY_PACKETS
product: Windows
targetos: Windows
req.typenames: IRB_REQ_RECEIVE_PHY_PACKETS
---

# _IRB_RECEIVE_PHY_PACKETS structure


## -description


This structure contains the fields necessary to carry out a ReceivePhyPackets request.


## -syntax


````
typedef struct _IRB_REQ_RECEIVE_PHY_PACKETS {
  ULONG                        Flags;
  PBUS_PHY_PACKET_NOTIFICATION PhyPacketRoutine;
  PVOID                        PhyPacketContext;
} IRB_REQ_RECEIVE_PHY_PACKETS;
````


## -struct-fields




### -field Flags

Specifies whether a callback should be registered or deactivated. Use REGISTER_PHY_PACKET_NOTIFICATION to register PhyPacketRoutine as the callback. Use DEREGISTER_PHY_PACKET_NOTIFICATION to deactivate any previously registered callbacks.


### -field PhyPacketRoutine

Points to the notification routine for received PHY packets. The following prototype illustrates the notification routine:

<pre class="syntax" xml:space="preserve"><code>void PhyPacketRoutine(
    __in PVOID           Context,
    __in ULONG           GenerationCount,
    __in ULARGE_INTEGER  PhyPacket
);</code></pre>


<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="Context"></a><a id="context"></a><a id="CONTEXT"></a><b>Context</b>

</td>
<td width="60%">
The argument that is specified in the <b>u.ReceivePhyPackets.PhyPacketContext</b> parameter when the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">REQUEST_RECEIVE_PHY_PACKET</a> request is sent.

</td>
</tr>
<tr>
<td width="40%">
<a id="GenerationCount"></a><a id="generationcount"></a><a id="GENERATIONCOUNT"></a><b>GenerationCount</b>

</td>
<td width="60%">
The generation count of the bus for this PHY packet.

</td>
</tr>
<tr>
<td width="40%">
<a id="PhyPacket"></a><a id="phypacket"></a><a id="PHYPACKET"></a><b>PhyPacket</b>

</td>
<td width="60%">
The 64-bit PHY packet that is received from the 1394 bus.

</td>
</tr>
</table>
 


### -field PhyPacketContext

Specifies the Context argument to be passed to the PhyPacketRoutine.

