---
UID: NI:ntddcdrm.IOCTL_CDROM_ENABLE_STREAMING
title: IOCTL_CDROM_ENABLE_STREAMING
author: windows-driver-content
description: Enables or disables CDROM streaming mode on a per-handle basis for raw read and write requests.
old-location: storage\ioctl_cdrom_enable_streaming.htm
old-project: storage
ms.assetid: DC31EABA-CE58-4B6F-ADCD-0BF72A92C6AB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_CDROM_ENABLE_STREAMING, IOCTL_CDROM_ENABLE_STREAMING control code [Storage Devices], ntddcdrm/IOCTL_CDROM_ENABLE_STREAMING, storage.ioctl_cdrom_enable_streaming
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. 

Because of  status code propagation from other APIs, the <b>Status</b> field can be set to (but not limited to) the following:




#### -STATUS_SUCCESS

The request completed successfully.


#### -STATUS_INFO_LENGTH_MISMATCH

The input buffer length is smaller than required.


#### -STATUS_INVALID_PARAMETER

The request type is not one of the four in types defined in the <b>STREAMING_CONTROL_REQUEST_TYPE</b> enumeration.


#### -STATUS_INVALID_HANDLE

Cannot find the file object context in the request.


#### -STATUS_INVALID_DEVICE_REQUEST

The requested streaming mode is not supported.


## -remarks



By default, streaming is disabled for all newly opened raw CDROM handles. A playback application that does not want to use the  file system and prefers to work with raw data should open two file handles for the same device: a regular one for file system metadata and a streaming one for real-time files.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/gg441238">CDROM_STREAMING_CONTROL</a>



<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_ENABLE_STREAMING control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

