---
UID: NI:ntddstor.IOCTL_STORAGE_DEVICE_POWER_CAP
title: IOCTL_STORAGE_DEVICE_POWER_CAP (ntddstor.h)
description: A driver can use IOCTL_STORAGE_DEVICE_POWER_CAP to specify a maximum operational power consumption level for a storage device.
old-location: storage\ioctl_storage_device_power_cap.htm
tech.root: storage
ms.assetid: 88DEC1F2-F0E7-4E95-9A46-D9E8EF72B1BB
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL"]
ms.keywords: IOCTL_STORAGE_DEVICE_POWER_CAP, IOCTL_STORAGE_DEVICE_POWER_CAP control, IOCTL_STORAGE_DEVICE_POWER_CAP control code [Storage Devices], ntddstor/IOCTL_STORAGE_DEVICE_POWER_CAP, storage.ioctl_storage_device_power_cap
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_DEVICE_POWER_CAP"
 - "IOCTL_STORAGE_DEVICE_POWER_CAP"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_DEVICE_POWER_CAP
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL


## -description


A driver can use <b>IOCTL_STORAGE_DEVICE_POWER_CAP</b> to specify a maximum operational power  consumption level for a storage device. The OS will do it's best to transition the device to a power state that will not exceed the given maximum. However, this depends on what the device supports. The actual maximum may be less than or greater than the desired maximum.


## -ioctlparameters




### -input-buffer

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be >= <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a>).

<b>
       Irp->AssociatedIrp.SystemBuffer</b> contains <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a> data that specifies the maximum power. 

<b>
       Parameters.DeviceIoControl.OutputBufferLength</b> indicates the number of bytes that can be written to <b>Irp->AssociatedIrp.SystemBuffer</b>. <b>OutputBufferLength</b> must be <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a>).


### -input-buffer-length

The length of .


### -output-buffer

If the operation is successful, the output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> will contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a> structure.   


### -output-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be >= <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a>).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_power_cap">STORAGE_DEVICE_POWER_CAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-_storage_device_power_cap_units">STORAGE_DEVICE_POWER_CAP_UNITS</a>
 

 

