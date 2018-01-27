---
UID: NI:ntddstor.IOCTL_STORAGE_LOAD_MEDIA2
title: IOCTL_STORAGE_LOAD_MEDIA2
author: windows-driver-content
description: Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES.
old-location: storage\ioctl_storage_load_media2.htm
old-project: storage
ms.assetid: ba458d46-9b5f-4ee3-80fa-59277e97fb4a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_load_media2, IOCTL_STORAGE_LOAD_MEDIA2 control code [Storage Devices], IOCTL_STORAGE_LOAD_MEDIA2, ntddstor/IOCTL_STORAGE_LOAD_MEDIA2, k307_3952f49a-8ca1-42eb-afd0-cb0e6eef66fc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	Ntddstor.h
apiname: 
-	IOCTL_STORAGE_LOAD_MEDIA2
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_LOAD_MEDIA2 IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES. Because no file system is mounted when a device is opened in this way, this request can be processed much more quickly than an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_load_media.md">IOCTL_STORAGE_LOAD_MEDIA</a> request.

Input, output, and I/O status block values for IOCTL_STORAGE_LOAD_MEDIA2 are identical to those for IOCTL_STORAGE_LOAD_MEDIA.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, STATUS_BUFFER_TOO_SMALL, or STATUS_DEVICE_NOT_CONNECTED.


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_load_media.md">IOCTL_STORAGE_LOAD_MEDIA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_LOAD_MEDIA2 control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

