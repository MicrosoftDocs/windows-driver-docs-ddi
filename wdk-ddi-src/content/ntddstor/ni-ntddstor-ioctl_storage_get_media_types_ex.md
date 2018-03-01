---
UID: NI:ntddstor.IOCTL_STORAGE_GET_MEDIA_TYPES_EX
title: IOCTL_STORAGE_GET_MEDIA_TYPES_EX
author: windows-driver-content
description: Returns information about the types of media supported by a device.
old-location: storage\ioctl_storage_get_media_types_ex.htm
old-project: storage
ms.assetid: 706269d8-123b-48c6-83cb-8ae47fb92efc
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_MEDIA_TYPES_EX IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns information about the types of media supported by a device. A storage class driver must handle this IOCTL to control devices to be accessed by the removable storage manager (RSM) either as stand-alone devices or as data transfer elements (drives) in a media library or changer device. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns an array of <a href="..\minitape\ns-minitape-_device_media_info.md">DEVICE_MEDIA_INFO</a> structures, one for each media type supported by the device, embedded in a <a href="..\minitape\ns-minitape-_get_media_types.md">GET_MEDIA_TYPES</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof(</b>GET_MEDIA_TYPES<b>)</b> plus additional device-type-specific data, if any.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH or STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\minitape\ns-minitape-_device_media_info.md">DEVICE_MEDIA_INFO</a>



<a href="..\minitape\ns-minitape-_get_media_types.md">GET_MEDIA_TYPES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_GET_MEDIA_TYPES_EX control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

