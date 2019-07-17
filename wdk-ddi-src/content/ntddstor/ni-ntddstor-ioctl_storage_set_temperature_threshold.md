---
UID: NI:ntddstor.IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
title: IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD (ntddstor.h)
description: A driver can use IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD to set the temperature threshold of a storage device (when supported by the hardware).
old-location: storage\ioctl_storage_set_temperature_threshold.htm
tech.root: storage
ms.assetid: 5D7348DC-1114-4346-9486-FCCE2C0F3E0F
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD, IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD control, IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD control code [Storage Devices], ntddstor/IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD, storage.ioctl_storage_set_temperature_threshold
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD"
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
- ntddstor.h
api_name:
- IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD IOCTL


## -description


A driver can use <b>IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</b> to set the temperature threshold of a storage device (when supported by the hardware).  Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to determine if the device supports changing the over and under temperature thresholds.


## -ioctlparameters




### -input-buffer

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_temperature_threshold">STORAGE_TEMPERATURE_THRESHOLD</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_temperature_threshold">STORAGE_TEMPERATURE_THRESHOLD</a>). 


### -output-buffer

This IOCTL has no output structure.


### -output-buffer-length

This IOCTL has no output structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>
 

 

