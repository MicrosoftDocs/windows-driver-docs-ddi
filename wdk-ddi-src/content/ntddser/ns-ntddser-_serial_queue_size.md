---
UID: NS:ntddser._SERIAL_QUEUE_SIZE
title: _SERIAL_QUEUE_SIZE (ntddser.h)
description: The SERIAL_QUEUE_SIZE structure is used to resize the input buffer that the serial controller driver uses for serial receive operations.
old-location: serports\serial_queue_size.htm
tech.root: serports
ms.assetid: 5EEE0B7D-2857-42D1-A387-9D38DAC2E368
ms.date: 04/23/2018
keywords: ["SERIAL_QUEUE_SIZE structure"]
ms.keywords: "*PSERIAL_QUEUE_SIZE, PSERIAL_QUEUE_SIZE, PSERIAL_QUEUE_SIZE structure pointer [Serial Ports], SERIAL_QUEUE_SIZE, SERIAL_QUEUE_SIZE structure [Serial Ports], _SERIAL_QUEUE_SIZE, ntddser/PSERIAL_QUEUE_SIZE, ntddser/SERIAL_QUEUE_SIZE, serports.serial_queue_size"
req.header: ntddser.h
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
targetos: Windows
req.typenames: SERIAL_QUEUE_SIZE, *PSERIAL_QUEUE_SIZE
f1_keywords:
 - _SERIAL_QUEUE_SIZE
 - ntddser/_SERIAL_QUEUE_SIZE
 - PSERIAL_QUEUE_SIZE
 - ntddser/PSERIAL_QUEUE_SIZE
 - SERIAL_QUEUE_SIZE
 - ntddser/SERIAL_QUEUE_SIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - SERIAL_QUEUE_SIZE
---

# _SERIAL_QUEUE_SIZE structure


## -description

The <b>SERIAL_QUEUE_SIZE</b> structure is used to resize the input buffer that the serial controller driver uses for serial receive operations.

## -struct-fields

### -field InSize

Number of bytes requested for the input buffer. For more information, see Remarks.

### -field OutSize

Not used. Set to zero.

## -remarks

This structure is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_queue_size">IOCTL_SERIAL_SET_QUEUE_SIZE</a> requests to specify the size requested for the new input buffer. This buffer is used internally by the serial controller driver to hold data received from the serial controller until the data can be copied to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> request packet. If the requested buffer size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_queue_size">IOCTL_SERIAL_SET_QUEUE_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>

