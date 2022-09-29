---
UID: NS:bthxddi._BTHX_HCI_READ_WRITE_CONTEXT
title: _BTHX_HCI_READ_WRITE_CONTEXT (bthxddi.h)
description: The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs.
old-location: bltooth\bthx_hci_read_write_context.htm
tech.root: bltooth
ms.date: 12/01/2021
keywords: ["BTHX_HCI_READ_WRITE_CONTEXT structure"]
ms.keywords: "*PBTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT, BTHX_HCI_READ_WRITE_CONTEXT structure [Bluetooth Devices], PBTHX_HCI_READ_WRITE_CONTEXT, PBTHX_HCI_READ_WRITE_CONTEXT structure pointer [Bluetooth Devices], _BTHX_HCI_READ_WRITE_CONTEXT, bltooth.bthx_hci_read_write_context, bthxddi/BTHX_HCI_READ_WRITE_CONTEXT, bthxddi/PBTHX_HCI_READ_WRITE_CONTEXT"
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
targetos: Windows
req.typenames: BTHX_HCI_READ_WRITE_CONTEXT, *PBTHX_HCI_READ_WRITE_CONTEXT
f1_keywords:
 - _BTHX_HCI_READ_WRITE_CONTEXT
 - bthxddi/_BTHX_HCI_READ_WRITE_CONTEXT
 - PBTHX_HCI_READ_WRITE_CONTEXT
 - bthxddi/PBTHX_HCI_READ_WRITE_CONTEXT
 - BTHX_HCI_READ_WRITE_CONTEXT
 - bthxddi/BTHX_HCI_READ_WRITE_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthXDDI.h
api_name:
 - _BTHX_HCI_READ_WRITE_CONTEXT
 - PBTHX_HCI_READ_WRITE_CONTEXT
 - BTHX_HCI_READ_WRITE_CONTEXT
---

# _BTHX_HCI_READ_WRITE_CONTEXT structure

## -description

The **BTHX_HCI_READ_WRITE_CONTEXT** structure is used by [IOCTL_BTHX_HCI_READ](./ni-bthxddi-ioctl_bthx_read_hci.md) and [IOCTL_BTHX_HCI_WRITE](./ni-bthxddi-ioctl_bthx_write_hci.md) for input and output.

## -struct-fields

### -field DataLen

The length of data contained in the **Data** field, in bytes.

### -field Type

The type of packetized data.

### -field Data

Actual data to be read/written.

## -remarks

The **BTHX_HCI_READ_WRITE_CONTEXT** structure is an input parameter to [IOCTL_BTHX_HCI_WRITE](./ni-bthxddi-ioctl_bthx_write_hci.md) and specifies the type of packet associated with the write. It also specifies the data to be written in the **Data** member.

This structure is also used as an output parameter for [IOCTL_BTHX_HCI_READ](./ni-bthxddi-ioctl_bthx_read_hci.md) and specifies the type of packet and the data associated with the read.

This structure is packed to 1-byte boundary.

## -see-also

- [IOCTL_BTHX_HCI_WRITE](./ni-bthxddi-ioctl_bthx_write_hci.md)
- [IOCTL_BTHX_HCI_READ](./ni-bthxddi-ioctl_bthx_read_hci.md)