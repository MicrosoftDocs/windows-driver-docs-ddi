---
UID: NI:ntddcdrm.IOCTL_CDROM_ENABLE_STREAMING
title: IOCTL_CDROM_ENABLE_STREAMING (ntddcdrm.h)
description: Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests.
old-location: storage\ioctl_cdrom_enable_streaming.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_ENABLE_STREAMING IOCTL"]
ms.keywords: IOCTL_CDROM_ENABLE_STREAMING, IOCTL_CDROM_ENABLE_STREAMING control, IOCTL_CDROM_ENABLE_STREAMING control code [Storage Devices], ntddcdrm/IOCTL_CDROM_ENABLE_STREAMING, storage.ioctl_cdrom_enable_streaming
req.header: ntddcdrm.h
req.include-header: Winioctl.h
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
req.typenames: 
f1_keywords:
 - IOCTL_CDROM_ENABLE_STREAMING
 - ntddcdrm/IOCTL_CDROM_ENABLE_STREAMING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - IOCTL_CDROM_ENABLE_STREAMING
---

# IOCTL_CDROM_ENABLE_STREAMING IOCTL


## -description

Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests. 

To perform this operation, call the 
   <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> 
   function and specify the <b>IOCTL_CDROM_ENABLE_STREAMING</b> I/O control request as the <i>dwIoControlCode</i> parameter.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_streaming_control">CDROM_STREAMING_CONTROL</a>

### -input-buffer-length

Length of a <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_streaming_control">CDROM_STREAMING_CONTROL</a>.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes returned. 

Because of  status code propagation from other APIs, the <b>Status</b> field can be set to (but not limited to) the following:




**STATUS_INFO_LENGTH_MISMATCH**

The input buffer length is smaller than required.


**STATUS_INVALID_DEVICE_REQUEST**

The requested streaming mode is not supported.


**STATUS_INVALID_HANDLE**

Cannot find the file object context in the request.


**STATUS_INVALID_PARAMETER**

The request type is not one of the four in types defined in the <b>STREAMING_CONTROL_REQUEST_TYPE</b> enumeration.


**STATUS_SUCCESS**

The request completed successfully.

## -remarks

By default, streaming is disabled for all newly opened raw CDROM handles. A playback application that does not want to use the  file system and prefers to work with raw data should open two file handles for the same device: a regular one for file system metadata and a streaming one for real-time files.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_streaming_control">CDROM_STREAMING_CONTROL</a>



<a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>
