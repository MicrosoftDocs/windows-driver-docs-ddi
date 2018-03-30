---
UID: NI:ntddstor.IOCTL_STORAGE_GET_HOTPLUG_INFO
title: IOCTL_STORAGE_GET_HOTPLUG_INFO
author: windows-driver-content
description: Retrieves the hotplug configuration of the specified device.
old-location: storage\ioctl_storage_get_hotplug_info.htm
old-project: storage
ms.assetid: e549aa75-d847-4276-ab40-29214b0475cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_STORAGE_GET_HOTPLUG_INFO, IOCTL_STORAGE_GET_HOTPLUG_INFO control code [Storage Devices], k307_06a9c82a-ee57-421f-befc-0a9da3543b40.xml, ntddstor/IOCTL_STORAGE_GET_HOTPLUG_INFO, storage.ioctl_storage_get_hotplug_info
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
-	IOCTL_STORAGE_GET_HOTPLUG_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_HOTPLUG_INFO IOCTL


## -description



Retrieves the hotplug configuration of the specified device. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the hotplug configuration data in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566987">STORAGE_HOTPLUG_INFO</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be greater than or equal to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL if the output buffer is too small.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560606">IOCTL_STORAGE_SET_HOTPLUG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566987">STORAGE_HOTPLUG_INFO</a>
 

 

