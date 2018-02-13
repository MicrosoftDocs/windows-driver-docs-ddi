---
UID: NI:ntddstor.IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
title: IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD to set the temperature threshold of a storage device (when supported by the hardware).
old-location: storage\ioctl_storage_set_temperature_threshold.htm
old-project: storage
ms.assetid: 5D7348DC-1114-4346-9486-FCCE2C0F3E0F
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_set_temperature_threshold, IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD control code [Storage Devices], IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD, ntddstor/IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
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
-	ntddstor.h
apiname:
-	IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


A driver can use <b>IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</b> to set the temperature threshold of a storage device (when supported by the hardware).  Use <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to determine if the device supports changing the over and under temperature thresholds.


## -ioctlparameters




### -input-buffer

A <a href="..\ntddstor\ns-ntddstor-_storage_temperature_threshold.md">STORAGE_TEMPERATURE_THRESHOLD</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_temperature_threshold.md">STORAGE_TEMPERATURE_THRESHOLD</a>). 


### -output-buffer

This IOCTL has no output structure.


### -output-buffer-length

This IOCTL has no output structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>



<a href="..\ntddstor\ns-ntddstor-_storage_temperature_info.md">STORAGE_TEMPERATURE_INFO</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

