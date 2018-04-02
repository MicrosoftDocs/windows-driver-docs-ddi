---
UID: NS:ntddstor._STORAGE_TEMPERATURE_THRESHOLD
title: "_STORAGE_TEMPERATURE_THRESHOLD"
author: windows-driver-content
description: This structure is used to set the over or under temperature threshold of a storage device (via IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD).
old-location: storage\storage_temperature_threshold.htm
old-project: storage
ms.assetid: 19096AD2-5149-4AE1-94CD-9004ED8C24DC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_TEMPERATURE_THRESHOLD, PSTORAGE_TEMPERATURE_THRESHOLD, PSTORAGE_TEMPERATURE_THRESHOLD structure pointer [Storage Devices], STORAGE_TEMPERATURE_THRESHOLD, STORAGE_TEMPERATURE_THRESHOLD structure [Storage Devices], _STORAGE_TEMPERATURE_THRESHOLD, ntddstor/PSTORAGE_TEMPERATURE_THRESHOLD, ntddstor/STORAGE_TEMPERATURE_THRESHOLD, storage.storage_temperature_threshold"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	STORAGE_TEMPERATURE_THRESHOLD
product: Windows
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_THRESHOLD, *PSTORAGE_TEMPERATURE_THRESHOLD
---

# _STORAGE_TEMPERATURE_THRESHOLD structure


## -description


This structure is used to set the over or under temperature threshold of a storage device (via <a href="https://msdn.microsoft.com/library/windows/hardware/mt650982">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>).


## -struct-fields




### -field Version

The version of the structure.


### -field Size

The size of this structure. This should be set to sizeof(<b>STORAGE_TEMPERATURE_THRESHOLD</b>).


### -field Flags

Flags set for this request. The following are valid flags.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_COMMAND_FLAG_ADAPTER_REQUEST</b></td>
<td>This flag indicates the request to target an adapter instead of device.</td>
</tr>
</table>
 


### -field Index

Identifies the instance of temperature information. Starts from 0. Index 0 may indicate a composite value.


### -field Threshold

A signed value that indicates the temperature of the threshold, in degrees Celsius.


### -field OverThreshold

Indicates if the <i>Threshold</i> specifies the over or under temperature threshold. If <b>true</b>, set the <b>OverThreshold</b> temperature value of the device; otherwise, set the <b>UnderThreshold</b> temperature value. 


### -field Reserved

Reserved for future use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt651018">STORAGE_TEMPERATURE_INFO</a>
 

 

