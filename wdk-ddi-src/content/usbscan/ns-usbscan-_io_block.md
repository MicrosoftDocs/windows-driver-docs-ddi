---
UID: NS:usbscan._IO_BLOCK
title: _IO_BLOCK (usbscan.h)
description: The IO_BLOCK structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_READ_REGISTERS or IOCTL_WRITE_REGISTERS.
old-location: image\io_block.htm
tech.root: image
ms.assetid: aa1ccffc-c742-415d-8b72-fef247dff03c
ms.date: 05/03/2018
ms.keywords: "*PIO_BLOCK, IO_BLOCK, IO_BLOCK structure [Imaging Devices], PIO_BLOCK, PIO_BLOCK structure pointer [Imaging Devices], _IO_BLOCK, image.io_block, stifnc_94187a6f-5c01-4d4a-a852-469f93d891b9.xml, usbscan/IO_BLOCK, usbscan/PIO_BLOCK"
ms.topic: struct
f1_keywords:
 - "usbscan/IO_BLOCK"
req.header: usbscan.h
req.include-header: Usbscan.h
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
- usbscan.h
api_name:
- IO_BLOCK
product:
- Windows
targetos: Windows
req.typenames: IO_BLOCK, *PIO_BLOCK
---

# _IO_BLOCK structure


## -description


The IO_BLOCK structure is used as a parameter to <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_read_registers">IOCTL_READ_REGISTERS</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_write_registers">IOCTL_WRITE_REGISTERS</a>. Values contained in structure members are used to create a USB Device Request (described in the <i>Universal Serial Bus Specification</i>).


## -struct-fields




### -field uOffset

Used as the <b>Value</b> field of a USB Device Request.


### -field uLength

Length of the buffer to transfer.


### -field pbyData

Pointer to a data buffer with a length of <b>uLength</b>.


### -field uIndex

Used as the <b>Index</b> field of a USB Device Request.

