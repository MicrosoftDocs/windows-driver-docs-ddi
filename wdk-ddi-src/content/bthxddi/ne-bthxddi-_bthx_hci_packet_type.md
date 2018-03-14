---
UID: NE:bthxddi._BTHX_HCI_PACKET_TYPE
title: "_BTHX_HCI_PACKET_TYPE"
author: windows-driver-content
description: The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver.
old-location: bltooth\bthx_hci_packet_type.htm
old-project: bltooth
ms.assetid: 87265ABB-C2B7-468F-83FC-411AD9769517
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BTHX_HCI_PACKET_TYPE, BTHX_HCI_PACKET_TYPE enumeration [Bluetooth Devices], HciPacketAclData, HciPacketCommand, HciPacketEvent, _BTHX_HCI_PACKET_TYPE, bltooth.bthx_hci_packet_type, bthxddi/BTHX_HCI_PACKET_TYPE, bthxddi/HciPacketAclData, bthxddi/HciPacketCommand, bthxddi/HciPacketEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthxddi.h
req.include-header: BthXDDI.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported starting with  Windows 8.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	BthXDDI.h
api_name:
-	BTHX_HCI_PACKET_TYPE
product: Windows
targetos: Windows
req.typenames: BTHX_HCI_PACKET_TYPE
---

# _BTHX_HCI_PACKET_TYPE enumeration


## -description


The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver.


## -syntax


````
typedef enum _BTHX_HCI_PACKET_TYPE { 
  HciPacketCommand  = 0x01,
  HciPacketAclData  = 0x02,
  HciPacketEvent    = 0x04
} BTHX_HCI_PACKET_TYPE;
````


## -enum-fields




### -field HciPacketCommand

The packet represents a command.


### -field HciPacketAclData

The packet represents ACL data.


### -field HciPacketEvent

The packet represents an event.


## -remarks



The IOCTL_BTHX_HCI_READ and IOCTL_BTHX_HCI_WRITE IOCTLs are used to read/write data to/from the transport driver. The BTHX_HCI_PACKET_TYPE enumeration is used to specify with which type of packet the read/write is associated.




## -see-also

<a href="..\bthxddi\ni-bthxddi-ioctl_bthx_read_hci.md">IOCTL_BTHX_HCI_READ</a>



<a href="..\bthxddi\ni-bthxddi-ioctl_bthx_write_hci.md">IOCTL_BTHX_HCI_WRITE</a>



 

 


