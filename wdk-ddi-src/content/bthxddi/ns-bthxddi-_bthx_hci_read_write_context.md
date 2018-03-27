---
UID: NS:bthxddi._BTHX_HCI_READ_WRITE_CONTEXT
title: "_BTHX_HCI_READ_WRITE_CONTEXT"
author: windows-driver-content
description: The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.
old-location: bltooth\bthx_hci_read_write_context.htm
old-project: bltooth
ms.assetid: EC31A704-A264-4A77-B979-BFA59B42BA94
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT structure [Bluetooth Devices], PBTHX_HCI_READ_WRITE_CONTEXT, PBTHX_HCI_READ_WRITE_CONTEXT structure pointer [Bluetooth Devices], _BTHX_HCI_READ_WRITE_CONTEXT, bltooth.bthx_hci_read_write_context, bthxddi/BTHX_HCI_READ_WRITE_CONTEXT, bthxddi/PBTHX_HCI_READ_WRITE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	BthXDDI.h
api_name:
-	BTHX_HCI_READ_WRITE_CONTEXT
product: Windows
targetos: Windows
req.typenames: BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT
---

# _BTHX_HCI_READ_WRITE_CONTEXT structure


## -description


The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for  the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.


## -struct-fields




### -field DataLen

The length, in bytes, of data in <b>Data</b>.


### -field Type

The type of packetized data.


### -field Data

 




#### - Data[]

Actual data to be read/written.


## -remarks



The BTHX_HCI_READ_WRITE_CONTEXT structure is an input parameter to the <a href="https://msdn.microsoft.com/77BBF6AC-F5FA-4795-8898-6DC02983F573">IOCTL_BTHX_HCI_WRITE IOCTL</a> and specifies the type of packet associated with the write. It also specifies the data to be written in the <b>Data</b> member.

This structure is also used as an output parameter for the <a href="https://msdn.microsoft.com/02CC3534-D319-40C1-A73C-DEFC1F5709F7">IOCTL_BTHX_HCI_READ</a> IOCTL and specifies the type of packet and the data associated with the read.

This structure is packed to 1-byte boundary.



