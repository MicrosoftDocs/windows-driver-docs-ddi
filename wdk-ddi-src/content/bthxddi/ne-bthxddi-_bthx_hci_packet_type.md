---
UID: NE:bthxddi._BTHX_HCI_PACKET_TYPE
title: _BTHX_HCI_PACKET_TYPE (bthxddi.h)
description: The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver.
old-location: bltooth\bthx_hci_packet_type.htm
tech.root: bltooth
ms.assetid: 87265ABB-C2B7-468F-83FC-411AD9769517
ms.date: 04/27/2018
keywords: ["_BTHX_HCI_PACKET_TYPE enumeration"]
ms.keywords: BTHX_HCI_PACKET_TYPE, BTHX_HCI_PACKET_TYPE enumeration [Bluetooth Devices], HciPacketAclData, HciPacketCommand, HciPacketEvent, _BTHX_HCI_PACKET_TYPE, bltooth.bthx_hci_packet_type, bthxddi/BTHX_HCI_PACKET_TYPE, bthxddi/HciPacketAclData, bthxddi/HciPacketCommand, bthxddi/HciPacketEvent
f1_keywords:
 - "bthxddi/BTHX_HCI_PACKET_TYPE"
 - "BTHX_HCI_PACKET_TYPE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- BthXDDI.h
api_name:
- BTHX_HCI_PACKET_TYPE
targetos: Windows
req.typenames: BTHX_HCI_PACKET_TYPE
---

# _BTHX_HCI_PACKET_TYPE enumeration


## -description


The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthxddi/ni-bthxddi-ioctl_bthx_read_hci">IOCTL_BTHX_HCI_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthxddi/ni-bthxddi-ioctl_bthx_write_hci">IOCTL_BTHX_HCI_WRITE</a>
 

 

