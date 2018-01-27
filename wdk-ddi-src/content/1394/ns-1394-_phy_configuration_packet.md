---
UID: NS:1394._PHY_CONFIGURATION_PACKET
title: _PHY_CONFIGURATION_PACKET
author: windows-driver-content
description: The PHY_CONFIGURATION_PACKET structure contains a raw PHY configuration packet.
old-location: ieee\phy_configuration_packet.htm
old-project: IEEE
ms.assetid: 5a5acd4a-ad99-4b8c-b8ea-490a7b467e14
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PHY_CONFIGURATION_PACKET, _PHY_CONFIGURATION_PACKET, IEEE.phy_configuration_packet, *PPHY_CONFIGURATION_PACKET, PHY_CONFIGURATION_PACKET structure [Buses], 1394/PHY_CONFIGURATION_PACKET, 1394/PPHY_CONFIGURATION_PACKET, PPHY_CONFIGURATION_PACKET, 1394stct_1d0c74cf-13c7-455d-b51e-5e2f4f2a5c5a.xml, PPHY_CONFIGURATION_PACKET structure pointer [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	1394.h
apiname: 
-	PHY_CONFIGURATION_PACKET
product: Windows
targetos: Windows
req.typenames: PHY_CONFIGURATION_PACKET, *PPHY_CONFIGURATION_PACKET
---

# _PHY_CONFIGURATION_PACKET structure


## -description


The PHY_CONFIGURATION_PACKET structure contains a raw PHY configuration packet.


## -syntax


````
typedef struct _PHY_CONFIGURATION_PACKET {
  ULONG PCP_Phys_ID  :6;
  ULONG PCP_Packet_ID  :2;
  ULONG PCP_Gap_Count  :6;
  ULONG PCP_Set_Gap_Count  :1;
  ULONG PCP_Force_Root  :1;
  ULONG PCP_Reserved1  :8;
  ULONG PCP_Reserved2  :8;
  ULONG PCP_Inverse;
} PHY_CONFIGURATION_PACKET, *PPHY_CONFIGURATION_PACKET;
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20PHY_CONFIGURATION_PACKET structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

