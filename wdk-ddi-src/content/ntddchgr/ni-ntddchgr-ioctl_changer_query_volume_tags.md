---
UID: NI:ntddchgr.IOCTL_CHANGER_QUERY_VOLUME_TAGS
title: IOCTL_CHANGER_QUERY_VOLUME_TAGS
author: windows-driver-content
description: Returns volume tag information for the specified elements.
old-location: storage\ioctl_changer_query_volume_tags.htm
old-project: storage
ms.assetid: d2edc681-2a12-4281-81f5-147cf6c5e68f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CHANGER_QUERY_VOLUME_TAGS, IOCTL_CHANGER_QUERY_VOLUME_TAGS control, IOCTL_CHANGER_QUERY_VOLUME_TAGS control code [Storage Devices], k307_c43d8b06-0f12-4543-8a7c-bcd8a752b342.xml, ntddchgr/IOCTL_CHANGER_QUERY_VOLUME_TAGS, storage.ioctl_changer_query_volume_tags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_QUERY_VOLUME_TAGS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_QUERY_VOLUME_TAGS IOCTL


## -description



Returns volume tag information for the specified elements.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> indicates the starting element for which to return information, the action to perform, and a template to use when searching for volume IDs.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff551479">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>). 


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563961">READ_ELEMENT_ADDRESS_INFO</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the parameter buffer for output, which must be &gt;= <b>sizeof</b>(READ_ELEMENT_ADDRESS_INFO).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the correct output buffer size, in bytes. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_ELEMENT_ADDRESS. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563961">READ_ELEMENT_ADDRESS_INFO</a>
 

 

