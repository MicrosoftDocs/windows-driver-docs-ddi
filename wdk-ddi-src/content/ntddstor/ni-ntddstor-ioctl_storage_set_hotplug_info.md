---
UID: NI:ntddstor.IOCTL_STORAGE_SET_HOTPLUG_INFO
title: IOCTL_STORAGE_SET_HOTPLUG_INFO
author: windows-driver-content
description: Sets the hotplug configuration of the specified device.
old-location: storage\ioctl_storage_set_hotplug_info.htm
old-project: storage
ms.assetid: 5badc919-8663-4905-aaec-70f6b51ab2f1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_storage_set_hotplug_info, IOCTL_STORAGE_SET_HOTPLUG_INFO control code [Storage Devices], IOCTL_STORAGE_SET_HOTPLUG_INFO, ntddstor/IOCTL_STORAGE_SET_HOTPLUG_INFO, k307_f6fb6bb6-0058-4fa6-9d4f-2f964b1ef646.xml
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
-	IOCTL_STORAGE_SET_HOTPLUG_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_SET_HOTPLUG_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Sets the hotplug configuration of the specified device. This request takes a <a href="..\ntddstor\ns-ntddstor-_storage_hotplug_info.md">STORAGE_HOTPLUG_INFO</a> structure as input. The <b>DeviceHotplug</b> member of the STORAGE_HOTPLUG_INFO structure determines what action is taken. If the value of that member is nonzero, the value for the device's removal policy in the registry is set to <b>ExpectSurpriseRemoval</b> and all levels of caching are disabled. If the value of <b>DeviceHotplug</b> is zero, the removal policy is set to <b>ExpectOrderlyRemoval</b>, and caching might be selectively enabled. 




## -ioctlparameters




### -input-buffer

The input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be greater than or equal to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). 


### -output-buffer

The driver returns the hotplug configuration data in a STORAGE_HOTPLUG_INFO structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The length of a <a href="..\ntddstor\ns-ntddstor-_storage_hotplug_info.md">STORAGE_HOTPLUG_INFO</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH if the input buffer is too small. It is set to STATUS_INVALID_PARAMETER_1 if the <b>Size</b> member of STORAGE_HOTPLUG_INFO is not the size expected by the class driver for this device. It is set to STATUS_INVALID_PARAMETER_2 if the <b>MediaRemoveable</b> member has a value different from that held by the class driver. It is set to STATUS_INVALID_PARAMETER_3 if the <b>MediaHotplug</b> member has a value different from that held by the class driver, and it is set to STATUS_INVALID_PARAMETER_5 if the <b>WriteCacheEnableOverride</b> member has a value different from that held by the class driver.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_hotplug_info.md">STORAGE_HOTPLUG_INFO</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_hotplug_info.md">IOCTL_STORAGE_GET_HOTPLUG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_SET_HOTPLUG_INFO control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

