---
UID: NI:ntddstor.IOCTL_STORAGE_DEVICE_POWER_CAP
title: IOCTL_STORAGE_DEVICE_POWER_CAP
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_DEVICE_POWER_CAP to specify a maximum operational power consumption level for a storage device.
old-location: storage\ioctl_storage_device_power_cap.htm
old-project: storage
ms.assetid: 88DEC1F2-F0E7-4E95-9A46-D9E8EF72B1BB
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_device_power_cap, IOCTL_STORAGE_DEVICE_POWER_CAP control code [Storage Devices], IOCTL_STORAGE_DEVICE_POWER_CAP, ntddstor/IOCTL_STORAGE_DEVICE_POWER_CAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	IOCTL_STORAGE_DEVICE_POWER_CAP
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


A driver can use <b>IOCTL_STORAGE_DEVICE_POWER_CAP</b> to specify a maximum operational power  consumption level for a storage device. The OS will do it's best to transition the device to a power state that will not exceed the given maximum. However, this depends on what the device supports. The actual maximum may be less than or greater than the desired maximum.


## -ioctlparameters




### -input-buffer

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a>).

<b>
       Irp-&gt;AssociatedIrp.SystemBuffer</b> contains <a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a> data that specifies the maximum power. 

<b>
       Parameters.DeviceIoControl.OutputBufferLength</b> indicates the number of bytes that can be written to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. <b>OutputBufferLength</b> must be <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a>).


### -input-buffer-length

The length of .


### -output-buffer

If the operation is successful, the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> will contain a <a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a> structure.   


### -output-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a>).


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED. 


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_device_power_cap.md">STORAGE_DEVICE_POWER_CAP</a>

<a href="..\ntddstor\ne-ntddstor-_storage_device_power_cap_units.md">STORAGE_DEVICE_POWER_CAP_UNITS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_DEVICE_POWER_CAP control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

