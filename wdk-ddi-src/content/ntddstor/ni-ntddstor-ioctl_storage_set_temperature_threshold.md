---
UID: NI:ntddstor.IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
title: IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD to set the temperature threshold of a storage device (when supported by the hardware).
old-location: storage\ioctl_storage_set_temperature_threshold.htm
old-project: storage
ms.assetid: 5D7348DC-1114-4346-9486-FCCE2C0F3E0F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD, IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD control code [Storage Devices], ntddstor/IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD, storage.ioctl_storage_set_temperature_threshold
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
product:
- Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD IOCTL


## -description


A driver can use <b>IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</b> to set the temperature threshold of a storage device (when supported by the hardware).  Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> to determine if the device supports changing the over and under temperature thresholds.


## -ioctlparameters




### -input-buffer

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt651019">STORAGE_TEMPERATURE_THRESHOLD</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/mt651019">STORAGE_TEMPERATURE_THRESHOLD</a>). 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt651018">STORAGE_TEMPERATURE_INFO</a>
 

 

