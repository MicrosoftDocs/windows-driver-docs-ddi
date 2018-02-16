---
UID: NI:ntddstor.IOCTL_STORAGE_GET_HOTPLUG_INFO
title: IOCTL_STORAGE_GET_HOTPLUG_INFO
author: windows-driver-content
description: Retrieves the hotplug configuration of the specified device.
old-location: storage\ioctl_storage_get_hotplug_info.htm
old-project: storage
ms.assetid: e549aa75-d847-4276-ab40-29214b0475cf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_get_hotplug_info, IOCTL_STORAGE_GET_HOTPLUG_INFO control code [Storage Devices], IOCTL_STORAGE_GET_HOTPLUG_INFO, ntddstor/IOCTL_STORAGE_GET_HOTPLUG_INFO, k307_06a9c82a-ee57-421f-befc-0a9da3543b40.xml
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
-	IOCTL_STORAGE_GET_HOTPLUG_INFO
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_GET_HOTPLUG_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Retrieves the hotplug configuration of the specified device. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the hotplug configuration data in a <a href="..\ntddstor\ns-ntddstor-_storage_hotplug_info.md">STORAGE_HOTPLUG_INFO</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be greater than or equal to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(STORAGE_HOTPLUG_INFO). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL if the output buffer is too small.


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_set_hotplug_info.md">IOCTL_STORAGE_SET_HOTPLUG_INFO</a>



<a href="..\ntddstor\ns-ntddstor-_storage_hotplug_info.md">STORAGE_HOTPLUG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_GET_HOTPLUG_INFO control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

