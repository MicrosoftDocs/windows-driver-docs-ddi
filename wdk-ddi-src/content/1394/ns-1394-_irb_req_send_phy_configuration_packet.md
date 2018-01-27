---
UID: NS:1394._IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
title: _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
author: windows-driver-content
description: This structure contains the fields necessary to carry out a SendPhyConfigurationPacket request.
old-location: ieee\irb_req_send_phy_configuration_packet.htm
old-project: IEEE
ms.assetid: FCB87010-EA7D-495F-B58A-6E0322F9C846
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IRB_REQ_SEND_PHY_CONFIGURATION_PACKET structure [Buses], IEEE.irb_req_send_phy_configuration_packet, 1394/IRB_REQ_SEND_PHY_CONFIGURATION_PACKET, _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET, IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
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
-	IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
product: Windows
targetos: Windows
req.typenames: IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
---

# _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET structure


## -description


This structure contains the fields necessary to carry out a SendPhyConfigurationPacket request.


## -syntax


````
typedef struct _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET {
  PHY_CONFIGURATION_PACKET PhyConfigurationPacket;
} IRB_REQ_SEND_PHY_CONFIGURATION_PACKET;
````


## -struct-fields




### -field PhyConfigurationPacket

Points to the PHY_CONFIGURATION_PACKET structure.


## -remarks


The packet is sent to all nodes on the bus. See the <a href="http://go.microsoft.com/fwlink/p/?linkid=8729">IEEE 1394 Trade Association specification</a> website for a description of Phy packets.


