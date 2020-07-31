---
UID: NS:1394._IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
title: _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET (1394.h)
description: This structure contains the fields necessary to carry out a SendPhyConfigurationPacket request.
old-location: ieee\irb_req_send_phy_configuration_packet.htm
tech.root: IEEE
ms.assetid: FCB87010-EA7D-495F-B58A-6E0322F9C846
ms.date: 02/15/2018
keywords: ["_IRB_REQ_SEND_PHY_CONFIGURATION_PACKET structure"]
ms.keywords: 1394/IRB_REQ_SEND_PHY_CONFIGURATION_PACKET, IEEE.irb_req_send_phy_configuration_packet, IRB_REQ_SEND_PHY_CONFIGURATION_PACKET, IRB_REQ_SEND_PHY_CONFIGURATION_PACKET structure [Buses], _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
f1_keywords:
 - "1394/IRB_REQ_SEND_PHY_CONFIGURATION_PACKET"
 - "IRB_REQ_SEND_PHY_CONFIGURATION_PACKET"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 1394.h
api_name:
- IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
targetos: Windows
req.typenames: IRB_REQ_SEND_PHY_CONFIGURATION_PACKET
---

# _IRB_REQ_SEND_PHY_CONFIGURATION_PACKET structure


## -description


This structure contains the fields necessary to carry out a SendPhyConfigurationPacket request.


## -struct-fields




### -field PhyConfigurationPacket

Points to the PHY_CONFIGURATION_PACKET structure.


## -remarks



The packet is sent to all nodes on the bus. See the <a href="https://go.microsoft.com/fwlink/p/?linkid=8729">IEEE 1394 Trade Association specification</a> website for a description of Phy packets.



