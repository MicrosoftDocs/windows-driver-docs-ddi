---
UID: NI:ntddstor.IOCTL_STORAGE_GET_MEDIA_TYPES_EX
title: IOCTL_STORAGE_GET_MEDIA_TYPES_EX
author: windows-driver-content
description: Returns information about the types of media supported by a device.
old-location: storage\ioctl_storage_get_media_types_ex.htm
old-project: storage
ms.assetid: 706269d8-123b-48c6-83cb-8ae47fb92efc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_GET_MEDIA_TYPES_EX, IOCTL_STORAGE_GET_MEDIA_TYPES_EX control code [Storage Devices], k307_6dad39e5-7a8b-477d-a96d-5f00fe7fee7b.xml, ntddstor/IOCTL_STORAGE_GET_MEDIA_TYPES_EX, storage.ioctl_storage_get_media_types_ex
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_GET_MEDIA_TYPES_EX
product:
- Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_MEDIA_TYPES_EX IOCTL


## -description



Returns information about the types of media supported by a device. A storage class driver must handle this IOCTL to control devices to be accessed by the removable storage manager (RSM) either as stand-alone devices or as data transfer elements (drives) in a media library or changer device. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552529">DEVICE_MEDIA_INFO</a> structures, one for each media type supported by the device, embedded in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554987">GET_MEDIA_TYPES</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof(</b>GET_MEDIA_TYPES<b>)</b> plus additional device-type-specific data, if any.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552529">DEVICE_MEDIA_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554987">GET_MEDIA_TYPES</a>
 

 

