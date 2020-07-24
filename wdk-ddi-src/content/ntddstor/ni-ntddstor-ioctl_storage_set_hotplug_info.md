---
UID: NI:ntddstor.IOCTL_STORAGE_SET_HOTPLUG_INFO
title: IOCTL_STORAGE_SET_HOTPLUG_INFO (ntddstor.h)
description: Sets the hotplug configuration of the specified device.
old-location: storage\ioctl_storage_set_hotplug_info.htm
tech.root: storage
ms.assetid: 5badc919-8663-4905-aaec-70f6b51ab2f1
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_SET_HOTPLUG_INFO IOCTL"]
ms.keywords: IOCTL_STORAGE_SET_HOTPLUG_INFO, IOCTL_STORAGE_SET_HOTPLUG_INFO control, IOCTL_STORAGE_SET_HOTPLUG_INFO control code [Storage Devices], k307_f6fb6bb6-0058-4fa6-9d4f-2f964b1ef646.xml, ntddstor/IOCTL_STORAGE_SET_HOTPLUG_INFO, storage.ioctl_storage_set_hotplug_info
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_SET_HOTPLUG_INFO"
 - "IOCTL_STORAGE_SET_HOTPLUG_INFO"
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
- IOCTL_STORAGE_SET_HOTPLUG_INFO
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_SET_HOTPLUG_INFO IOCTL


## -description



Sets the hotplug configuration of the specified device. This request takes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hotplug_info">STORAGE_HOTPLUG_INFO</a> structure as input. The <b>DeviceHotplug</b> member of the STORAGE_HOTPLUG_INFO structure determines what action is taken. If the value of that member is nonzero, the value for the device's removal policy in the registry is set to <b>ExpectSurpriseRemoval</b> and all levels of caching are disabled. If the value of <b>DeviceHotplug</b> is zero, the removal policy is set to <b>ExpectOrderlyRemoval</b>, and caching might be selectively enabled. 




## -ioctlparameters




### -input-buffer

The input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be greater than or equal to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). 


### -output-buffer

The driver returns the hotplug configuration data in a STORAGE_HOTPLUG_INFO structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hotplug_info">STORAGE_HOTPLUG_INFO</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH if the input buffer is too small. It is set to STATUS_INVALID_PARAMETER_1 if the <b>Size</b> member of STORAGE_HOTPLUG_INFO is not the size expected by the class driver for this device. It is set to STATUS_INVALID_PARAMETER_2 if the <b>MediaRemoveable</b> member has a value different from that held by the class driver. It is set to STATUS_INVALID_PARAMETER_3 if the <b>MediaHotplug</b> member has a value different from that held by the class driver, and it is set to STATUS_INVALID_PARAMETER_5 if the <b>WriteCacheEnableOverride</b> member has a value different from that held by the class driver.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_get_hotplug_info">IOCTL_STORAGE_GET_HOTPLUG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hotplug_info">STORAGE_HOTPLUG_INFO</a>
 

 

