---
UID: NI:ntddcdvd.IOCTL_STORAGE_SET_READ_AHEAD
title: IOCTL_STORAGE_SET_READ_AHEAD
author: windows-driver-content
description: Causes the device to skip to the given target address when the device reaches a certain trigger address during read-ahead caching.
old-location: storage\ioctl_storage_set_read_ahead.htm
old-project: storage
ms.assetid: a7ed65f3-40a9-4b08-b59d-7c65c250d5cb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_set_read_ahead, IOCTL_STORAGE_SET_READ_AHEAD control code [Storage Devices], IOCTL_STORAGE_SET_READ_AHEAD, ntddcdvd/IOCTL_STORAGE_SET_READ_AHEAD, k307_0112afc4-1b4b-47c1-9ace-1d82a41b120f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	Ntddcdvd.h
apiname:
-	IOCTL_STORAGE_SET_READ_AHEAD
product: Windows
targetos: Windows
req.typenames: "*PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT"
---

# IOCTL_STORAGE_SET_READ_AHEAD IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Causes the device to skip to the given target address when the device reaches a certain trigger address during read-ahead caching. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-_storage_set_read_ahead.md">STORAGE_SET_READ_AHEAD</a> structure that indicates the trigger and target addresses. 


### -input-buffer-length

The length of a <a href="..\ntddcdvd\ns-ntddcdvd-_storage_set_read_ahead.md">STORAGE_SET_READ_AHEAD</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS.


## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_storage_set_read_ahead.md">STORAGE_SET_READ_AHEAD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_SET_READ_AHEAD control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

