---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_NUMBER
title: IOCTL_STORAGE_GET_DEVICE_NUMBER (ntddstor.h)
description: Returns a STORAGE_DEVICE_NUMBER structure that contains the FILE_DEVICE_XXX type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started.
old-location: storage\ioctl_storage_get_device_number.htm
tech.root: storage
ms.assetid: 5d1095c6-b9f9-44ef-bb2b-7bc0265e5aa9
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_GET_DEVICE_NUMBER, IOCTL_STORAGE_GET_DEVICE_NUMBER control, IOCTL_STORAGE_GET_DEVICE_NUMBER control code [Storage Devices], k307_d4d6bd65-7f75-4810-90ce-edd3dec950be.xml, ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER, storage.ioctl_storage_get_device_number
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_GET_DEVICE_NUMBER
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_DEVICE_NUMBER IOCTL


## -description



Returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566974">STORAGE_DEVICE_NUMBER</a> structure that contains the FILE_DEVICE_<i>XXX</i> type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started. This request is usually issued by a fault-tolerant disk driver. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566974">STORAGE_DEVICE_NUMBER</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(STORAGE_DEVICE_NUMBER). 


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566974">STORAGE_DEVICE_NUMBER</a>
 

 

