---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_INFO_QUERY
title: "_STORAGE_HW_FIRMWARE_INFO_QUERY"
author: windows-driver-content
description: This structure contains information about the device firmware.
old-location: storage\storage_hw_firmware_info_query.htm
old-project: storage
ms.assetid: 7B58F050-2AF4-4BD5-95AB-254BCAA865F6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSTORAGE_HW_FIRMWARE_INFO_QUERY, ,, A, E, F, G, H, I, M, N, O, P, PSTORAGE_HW_FIRMWARE_INFO_QUERY, PSTORAGE_HW_FIRMWARE_INFO_QUERY structure pointer [Storage Devices], Q, R, S, STORAGE_HW_FIRMWARE_INFO_QUERY, STORAGE_HW_FIRMWARE_INFO_QUERY structure [Storage Devices], T, U, W, Y, _, _STORAGE_HW_FIRMWARE_INFO_QUERY, ntddstor/PSTORAGE_HW_FIRMWARE_INFO_QUERY, ntddstor/STORAGE_HW_FIRMWARE_INFO_QUERY, storage.storage_hw_firmware_info_query"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_HW_FIRMWARE_INFO_QUERY
product: Windows
targetos: Windows
req.typenames: STORAGE_HW_FIRMWARE_INFO_QUERY, *PSTORAGE_HW_FIRMWARE_INFO_QUERY
---

# _STORAGE_HW_FIRMWARE_INFO_QUERY structure


## -description


This structure contains information about the device firmware.


## -syntax


````
typedef struct _STORAGE_HW_FIRMWARE_INFO_QUERY {
  ULONG Version;
  ULONG Size;
  ULONG Flags;
  ULONG Reserved;
} STORAGE_HW_FIRMWARE_INFO_QUERY, *PSTORAGE_HW_FIRMWARE_INFO_QUERY;
````


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

