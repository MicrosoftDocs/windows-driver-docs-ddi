---
UID: NI:ntdddisk.IOCTL_DISK_SET_CACHE_INFORMATION
title: IOCTL_DISK_SET_CACHE_INFORMATION
author: windows-driver-content
description: Sets disk cache configuration data.
old-location: storage\ioctl_disk_set_cache_information.htm
old-project: storage
ms.assetid: ae1ca621-4862-4345-bb51-4a1c31e00542
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_disk_set_cache_information, IOCTL_DISK_SET_CACHE_INFORMATION control code [Storage Devices], IOCTL_DISK_SET_CACHE_INFORMATION, ntdddisk/IOCTL_DISK_SET_CACHE_INFORMATION, k307_4f1b855c-4788-48e9-bc26-7addf3c7e3a9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntdddisk.h
apiname: 
-	IOCTL_DISK_SET_CACHE_INFORMATION
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_SET_CACHE_INFORMATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Sets disk cache configuration data.




## -ioctlparameters




### -input-buffer

The input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS or STATUS_INFO_LENGTH_MISMATCH if the input buffer is not large enough. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_cache_information.md">DISK_CACHE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_SET_CACHE_INFORMATION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

