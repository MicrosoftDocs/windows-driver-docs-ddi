---
UID: NI:mountdev.IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
title: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
author: windows-driver-content
description: Support for this IOCTL by mount manager clients is mandatory.
old-location: storage\ioctl_mountdev_query_unique_id.htm
old-project: storage
ms.assetid: 866b9383-d73d-4be1-a4de-b78c9558c3ce
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control code [Storage Devices], k307_5dd8b350-65b5-4f59-b96f-cae11fe7fb5b.xml, mountdev/IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, storage.ioctl_mountdev_query_unique_id
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountdev.h
req.include-header: Mountdev.h
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
-	Mountdev.h
api_name:
-	IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
---

# IOCTL_MOUNTDEV_QUERY_UNIQUE_ID IOCTL


## -description


Support for this IOCTL by mount manager clients is mandatory. Upon receiving this IOCTL, the mount manager client must provide a counted byte string identifier that is unique to the client (that is, the device or the volume). The client cannot change this unique ID without alerting the mount manager (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560443">IOCTL_MOUNTDEV_UNIQUE_ID_CHANGE_NOTIFY</a>). 


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer

The device class or volume driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTDEV_UNIQUE_ID).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to FIELD_OFFSET(<a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a>, UniqueId) + output-&gt;UniqueIdLength; or alternatively to sizeof(USHORT) + output-&gt;UniqueIdLength, where output points to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560443">IOCTL_MOUNTDEV_UNIQUE_ID_CHANGE_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

