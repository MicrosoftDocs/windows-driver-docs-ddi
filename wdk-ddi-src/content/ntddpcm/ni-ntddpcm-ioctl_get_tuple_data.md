---
UID: NI:ntddpcm.IOCTL_GET_TUPLE_DATA
title: IOCTL_GET_TUPLE_DATA (ntddpcm.h)
description: This request retrieves tuple data that is stored in a PC Card's or CardBus card's attribute memory.
old-location: pcmcia\ioctl_get_tuple_data.htm
tech.root: PCMCIA
ms.assetid: 90bb06c3-2975-4290-b6f1-0c36e7b8678b
ms.date: 02/15/2018
keywords: ["IOCTL_GET_TUPLE_DATA IOCTL"]
ms.keywords: IOCTL_GET_TUPLE_DATA, IOCTL_GET_TUPLE_DATA control, IOCTL_GET_TUPLE_DATA control code [Buses], PCMCIA.ioctl_get_tuple_data, memcdref_80c1671e-c0c2-4429-b703-ffb389cc7af5.xml, ntddpcm/IOCTL_GET_TUPLE_DATA
f1_keywords:
 - "ntddpcm/IOCTL_GET_TUPLE_DATA"
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
- ntddpcm.h
api_name:
- IOCTL_GET_TUPLE_DATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GET_TUPLE_DATA IOCTL


## -description


This request retrieves tuple data that is stored in a PC Card's or CardBus card's attribute memory. The caller must specify the number of the socket where the PC Card or CardBus card is inserted, the location of an output buffer, and the number of bytes of tuple data to be read. 


## -ioctlparameters




### -input-buffer

The caller initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_tuple_request">TUPLE_REQUEST</a> structure, which is defined in <i>ntddpcm.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(TUPLE_REQUEST).


### -output-buffer

The PCMCIA bus driver stores the requested tuple data at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The size of the requested tuple data.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes read. 

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(TUPLE_REQUEST), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If the bus driver cannot identify a socket that is associated with the socket number indicated in TUPLE_REQUEST, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-write-config">IRP_MN_WRITE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_tuple_request">TUPLE_REQUEST</a>
 

 

