---
UID: NI:ntddpar.IOCTL_PAR_QUERY_RAW_DEVICE_ID
title: IOCTL_PAR_QUERY_RAW_DEVICE_ID (ntddpar.h)
description: The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following:\_a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the IEEE 1284 device ID; and a NULL terminator.
old-location: parports\ioctl_par_query_raw_device_id.htm
tech.root: parports
ms.date: 02/15/2018
keywords: ["IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL"]
ms.keywords: IOCTL_PAR_QUERY_RAW_DEVICE_ID, IOCTL_PAR_QUERY_RAW_DEVICE_ID control code [Parallel Ports], cisspd_422dd85c-1d22-4968-9b4c-fd1ef03432e5.xml, ntddpar/IOCTL_PAR_QUERY_RAW_DEVICE_ID, parports.ioctl_par_query_raw_device_id
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
f1_keywords:
 - IOCTL_PAR_QUERY_RAW_DEVICE_ID
 - ntddpar/IOCTL_PAR_QUERY_RAW_DEVICE_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddpar.h
api_name:
 - IOCTL_PAR_QUERY_RAW_DEVICE_ID
---

# IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the IEEE 1284 device ID; and a <b>NULL</b> terminator.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that the client allocates to output a raw device ID. The buffer contains the following contiguous sequence of information: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a <b>NULL</b> terminator.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of the output buffer that can hold the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a <b>NULL</b> terminator. An IEEE 1284 device ID can be up to 64 KB in size.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of the information returned in the output buffer. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The output buffer that <b>AssociatedIrp.SystemBuffer</b> points to is less than the size, in bytes, of a two-byte prefix, the IEEE 1284 device ID, and a <b>NULL</b> terminator.


**STATUS_IO_DEVICE_ERROR**

A device I/O error occurred.

## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id_size.md">IOCTL_PAR_QUERY_DEVICE_ID_SIZE</a>
