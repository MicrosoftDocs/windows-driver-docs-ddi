---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_INFO_QUERY
title: _STORAGE_HW_FIRMWARE_INFO_QUERY (ntddstor.h)
description: The _STORAGE_HW_FIRMWARE_INFO_QUERY structure contains information about the device firmware.
old-location: storage\storage_hw_firmware_info_query.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_HW_FIRMWARE_INFO_QUERY structure"]
ms.keywords: "*PSTORAGE_HW_FIRMWARE_INFO_QUERY, PSTORAGE_HW_FIRMWARE_INFO_QUERY, PSTORAGE_HW_FIRMWARE_INFO_QUERY structure pointer [Storage Devices], STORAGE_HW_FIRMWARE_INFO_QUERY, STORAGE_HW_FIRMWARE_INFO_QUERY structure [Storage Devices], _STORAGE_HW_FIRMWARE_INFO_QUERY, ntddstor/PSTORAGE_HW_FIRMWARE_INFO_QUERY, ntddstor/STORAGE_HW_FIRMWARE_INFO_QUERY, storage.storage_hw_firmware_info_query"
req.header: ntddstor.h
req.include-header: 
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
req.typenames: STORAGE_HW_FIRMWARE_INFO_QUERY, *PSTORAGE_HW_FIRMWARE_INFO_QUERY
f1_keywords:
 - _STORAGE_HW_FIRMWARE_INFO_QUERY
 - ntddstor/_STORAGE_HW_FIRMWARE_INFO_QUERY
 - PSTORAGE_HW_FIRMWARE_INFO_QUERY
 - ntddstor/PSTORAGE_HW_FIRMWARE_INFO_QUERY
 - STORAGE_HW_FIRMWARE_INFO_QUERY
 - ntddstor/STORAGE_HW_FIRMWARE_INFO_QUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_HW_FIRMWARE_INFO_QUERY
 - PSTORAGE_HW_FIRMWARE_INFO_QUERY
 - STORAGE_HW_FIRMWARE_INFO_QUERY
---

# _STORAGE_HW_FIRMWARE_INFO_QUERY structure


## -description

This structure contains information about the device firmware.

## -struct-fields

### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_INFO_QUERY)

### -field Size

The size of this structure as a buffer.

### -field Flags

The flags associated with the query. The following are flags that can be set in this member.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>STORAGE_HW_FIRMWARE_REQUEST_FLAG_CONTROLLER</td>
<td>Indicates that the target of the request is different than the device handle or object itself.</td>
</tr>
</table>

### -field Reserved

Reserved for future use.

