---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_NUMBER
title: IOCTL_STORAGE_GET_DEVICE_NUMBER
author: windows-driver-content
description: Returns a STORAGE_DEVICE_NUMBER structure that contains the FILE_DEVICE_XXX type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started.
old-location: storage\ioctl_storage_get_device_number.htm
old-project: storage
ms.assetid: 5d1095c6-b9f9-44ef-bb2b-7bc0265e5aa9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_STORAGE_GET_DEVICE_NUMBER, IOCTL_STORAGE_GET_DEVICE_NUMBER control code [Storage Devices], k307_d4d6bd65-7f75-4810-90ce-edd3dec950be.xml, ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER, storage.ioctl_storage_get_device_number
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
-	IOCTL_STORAGE_GET_DEVICE_NUMBER
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_DEVICE_NUMBER IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns a <a href="..\ntddstor\ns-ntddstor-_storage_device_number.md">STORAGE_DEVICE_NUMBER</a> structure that contains the FILE_DEVICE_<i>XXX</i> type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started. This request is usually issued by a fault-tolerant disk driver. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntddstor\ns-ntddstor-_storage_device_number.md">STORAGE_DEVICE_NUMBER</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(STORAGE_DEVICE_NUMBER). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_device_number.md">STORAGE_DEVICE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_GET_DEVICE_NUMBER control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

