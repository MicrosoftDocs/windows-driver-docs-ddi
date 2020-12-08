---
UID: NS:ntddstor._STORAGE_TEMPERATURE_THRESHOLD
title: _STORAGE_TEMPERATURE_THRESHOLD (ntddstor.h)
description: This structure is used to set the over or under temperature threshold of a storage device (via IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD).
old-location: storage\storage_temperature_threshold.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_TEMPERATURE_THRESHOLD structure"]
ms.keywords: "*PSTORAGE_TEMPERATURE_THRESHOLD, PSTORAGE_TEMPERATURE_THRESHOLD, PSTORAGE_TEMPERATURE_THRESHOLD structure pointer [Storage Devices], STORAGE_TEMPERATURE_THRESHOLD, STORAGE_TEMPERATURE_THRESHOLD structure [Storage Devices], _STORAGE_TEMPERATURE_THRESHOLD, ntddstor/PSTORAGE_TEMPERATURE_THRESHOLD, ntddstor/STORAGE_TEMPERATURE_THRESHOLD, storage.storage_temperature_threshold"
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
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_THRESHOLD, *PSTORAGE_TEMPERATURE_THRESHOLD
f1_keywords:
 - _STORAGE_TEMPERATURE_THRESHOLD
 - ntddstor/_STORAGE_TEMPERATURE_THRESHOLD
 - PSTORAGE_TEMPERATURE_THRESHOLD
 - ntddstor/PSTORAGE_TEMPERATURE_THRESHOLD
 - STORAGE_TEMPERATURE_THRESHOLD
 - ntddstor/STORAGE_TEMPERATURE_THRESHOLD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_TEMPERATURE_THRESHOLD
---

# _STORAGE_TEMPERATURE_THRESHOLD structure


## -description

This structure is used to set the over or under temperature threshold of a storage device (via <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_temperature_threshold">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>).

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

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>
