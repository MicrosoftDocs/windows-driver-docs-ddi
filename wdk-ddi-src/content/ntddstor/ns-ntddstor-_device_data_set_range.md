---
UID: NS:ntddstor._DEVICE_DATA_SET_RANGE
title: "_DEVICE_DATA_SET_RANGE"
author: windows-driver-content
description: The DEVICE_DATA_SET_RANGE structure specifies a block of data set ranges for the attributes for a device.
old-location: storage\device_data_set_range.htm
old-project: storage
ms.assetid: 9f610927-d8d0-44c5-8a66-0204953c1859
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEVICE_DATA_SET_RANGE, DEVICE_DATA_SET_RANGE, DEVICE_DATA_SET_RANGE structure [Storage Devices], PDEVICE_DATA_SET_RANGE, PDEVICE_DATA_SET_RANGE structure pointer [Storage Devices], _DEVICE_DATA_SET_RANGE, ntddstor/DEVICE_DATA_SET_RANGE, ntddstor/PDEVICE_DATA_SET_RANGE, storage.device_data_set_range, structs-general_28460ffa-da09-47af-9f30-6e991c422620.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	ntddstor.h
api_name:
-	DEVICE_DATA_SET_RANGE
product: Windows
targetos: Windows
req.typenames: DEVICE_DATA_SET_RANGE, *PDEVICE_DATA_SET_RANGE
---

# _DEVICE_DATA_SET_RANGE structure


## -description


The <b>DEVICE_DATA_SET_RANGE</b> structure specifies a block of data set ranges for the attributes for a device. 

The block of data set ranges is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure that is contained in the system buffer of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.


## -struct-fields




### -field StartingOffset

Contains the starting offset, in bytes, of the data set range. The offset value must be block aligned.


### -field LengthInBytes

Contains the length, in bytes, of the data set range. The length value must be block aligned.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

