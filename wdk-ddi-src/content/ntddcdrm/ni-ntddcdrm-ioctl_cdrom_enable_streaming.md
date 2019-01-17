---
UID: NI:ntddcdrm.IOCTL_CDROM_ENABLE_STREAMING
title: IOCTL_CDROM_ENABLE_STREAMING
description: Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests.
old-location: storage\ioctl_cdrom_enable_streaming.htm
tech.root: storage
ms.assetid: DC31EABA-CE58-4B6F-ADCD-0BF72A92C6AB
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_ENABLE_STREAMING, IOCTL_CDROM_ENABLE_STREAMING control, IOCTL_CDROM_ENABLE_STREAMING control code [Storage Devices], ntddcdrm/IOCTL_CDROM_ENABLE_STREAMING, storage.ioctl_cdrom_enable_streaming
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_ENABLE_STREAMING
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_ENABLE_STREAMING IOCTL


## -description


Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests. 

To perform this operation, call the 
   <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function and specify the <b>IOCTL_CDROM_ENABLE_STREAMING</b> I/O control request as the <i>dwIoControlCode</i> parameter.


## -ioctlparameters




### -input-buffer


<a href="https://msdn.microsoft.com/library/windows/hardware/gg441238">CDROM_STREAMING_CONTROL</a>



### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/gg441238">CDROM_STREAMING_CONTROL</a>.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. 

Because of  status code propagation from other APIs, the <b>Status</b> field can be set to (but not limited to) the following:




#### -STATUS_INFO_LENGTH_MISMATCH

The input buffer length is smaller than required.


#### -STATUS_INVALID_DEVICE_REQUEST

The requested streaming mode is not supported.


#### -STATUS_INVALID_HANDLE

Cannot find the file object context in the request.


#### -STATUS_INVALID_PARAMETER

The request type is not one of the four in types defined in the <b>STREAMING_CONTROL_REQUEST_TYPE</b> enumeration.


#### -STATUS_SUCCESS

The request completed successfully.


## -remarks



By default, streaming is disabled for all newly opened raw CDROM handles. A playback application that does not want to use the  file system and prefers to work with raw data should open two file handles for the same device: a regular one for file system metadata and a streaming one for real-time files.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/gg441238">CDROM_STREAMING_CONTROL</a>



<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>
 

 

