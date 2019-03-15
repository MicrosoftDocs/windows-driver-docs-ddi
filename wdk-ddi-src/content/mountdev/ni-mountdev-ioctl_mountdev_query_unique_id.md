---
UID: NI:mountdev.IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
title: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID (mountdev.h)
description: Support for this IOCTL by mount manager clients is mandatory.
old-location: storage\ioctl_mountdev_query_unique_id.htm
tech.root: storage
ms.assetid: 866b9383-d73d-4be1-a4de-b78c9558c3ce
ms.date: 03/29/2018
ms.keywords: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control, IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control code [Storage Devices], k307_5dd8b350-65b5-4f59-b96f-cae11fe7fb5b.xml, mountdev/IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, storage.ioctl_mountdev_query_unique_id
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Mountdev.h
api_name:
- IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTDEV_QUERY_UNIQUE_ID IOCTL

## -description

Support for this IOCTL by mount manager clients is mandatory. Upon receiving this IOCTL, the mount manager client must provide a counted byte string identifier that is unique to the client (that is, the device or the volume). The client cannot change this unique ID without alerting the mount manager (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560443">IOCTL_MOUNTDEV_UNIQUE_ID_CHANGE_NOTIFY</a>). 

## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer

The device class or volume driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTDEV_UNIQUE_ID).


### -in-out-buffer








### -inout-buffer-length



## -remarks

The implementer of this function must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls. 





### -status-block

The <b>Information</b> field is set to FIELD_OFFSET(<a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a>, UniqueId) + output-&gt;UniqueIdLength; or alternatively to sizeof(USHORT) + output-&gt;UniqueIdLength, where output points to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560443">IOCTL_MOUNTDEV_UNIQUE_ID_CHANGE_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562264">MOUNTDEV_UNIQUE_ID</a>
 

 

