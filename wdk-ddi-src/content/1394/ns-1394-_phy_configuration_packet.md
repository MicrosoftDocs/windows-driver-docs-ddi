---
UID: NS:1394._PHY_CONFIGURATION_PACKET
title: _PHY_CONFIGURATION_PACKET (1394.h)
description: The PHY_CONFIGURATION_PACKET structure contains a raw PHY configuration packet.
old-location: ieee\phy_configuration_packet.htm
tech.root: IEEE
ms.assetid: 5a5acd4a-ad99-4b8c-b8ea-490a7b467e14
ms.date: 02/15/2018
keywords: ["PHY_CONFIGURATION_PACKET structure"]
ms.keywords: "*PPHY_CONFIGURATION_PACKET, 1394/PHY_CONFIGURATION_PACKET, 1394/PPHY_CONFIGURATION_PACKET, 1394stct_1d0c74cf-13c7-455d-b51e-5e2f4f2a5c5a.xml, IEEE.phy_configuration_packet, PHY_CONFIGURATION_PACKET, PHY_CONFIGURATION_PACKET structure [Buses], PPHY_CONFIGURATION_PACKET, PPHY_CONFIGURATION_PACKET structure pointer [Buses], _PHY_CONFIGURATION_PACKET"
f1_keywords:
 - "1394/PHY_CONFIGURATION_PACKET"
 - "PHY_CONFIGURATION_PACKET"
req.header: 1394.h
req.include-header: 1394.h
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
- PHY_CONFIGURATION_PACKET
targetos: Windows
req.typenames: PHY_CONFIGURATION_PACKET, *PPHY_CONFIGURATION_PACKET
---

# _PHY_CONFIGURATION_PACKET structure


## -description


The PHY_CONFIGURATION_PACKET structure contains a raw PHY configuration packet.


## -struct-fields




### -field PCP_Phys_ID

Specifies the node address of the root. This member contains bits 0-5 of byte 0 of the packet. 


### -field PCP_Packet_ID

This member must be PHY_PACKET_ID_CONFIGURATION to indicate it is a PHY configuration packet. This member contains bits 6-7 of byte 0 of the packet. 


### -field PCP_Gap_Count

If the <b>PCP_Set_Gap_Count</b> bit is set, the PHY register gap_count field is set to this value. This member contains bits 0-5 of byte 1 of the packet. 


### -field PCP_Set_Gap_Count

If this bit is set, the PHY register gap_count field is set to <b>PCP_Gap_Count</b>. This member contains bit 6 of byte 1 of the packet. 


### -field PCP_Force_Root

If set, the caller becomes the root node. This member contains bit 7 of byte 1 of the packet. 


### -field PCP_Reserved1

Reserved. This member contains bits 0-7 of byte 2 of the packet. 


### -field PCP_Reserved2

Reserved. This member contains bits 0-7 of byte 3 of the packet. 


### -field PCP_Inverse

Specifies the logical inverse of the first quadlet of the packet. 


## -remarks



For an explanation of the function of the PHY configuration packet, see the IEEE 1394 specification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537661">REQUEST_SEND_PHY_CONFIG_PACKET</a>
 

 

