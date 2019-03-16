---
UID: NF:ntddk.MmMapViewInSystemSpace
title: MmMapViewInSystemSpace function (ntddk.h)
description: The MmMapViewInSystemSpace function maps the specified section into the system's address space.
ms.assetid: d7329479-9e00-4acc-81df-0e9a3ae212c0
ms.date: 10/19/2018
ms.topic: function
ms.keywords: MmMapViewInSystemSpace
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: "<=APC_LEVEL"
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NfcCx.dll
api_name: 
- MmMapViewInSystemSpace
product:
- Windows
targetos: Windows

ms.custom: RS5
---

# MmMapViewInSystemSpace function


## -description

The **MmMapViewInSystemSpace** function maps the specified section into the system's address space.

## -parameters

### -param Section
Supplies a pointer to the section to map.

### -param MappedBase
Contains the address where the section was mapped.

### -param ViewSize
Supplies the size of the view to map.  If this is specified as zero, the whole section is mapped. Returns the actual size mapped.

## -returns
This function returns true if the map view operation was successful.
## -remarks

## -see-also
[MmUnmapViewInSystemSpace](nf-ntddk-mmunmapviewinsystemspace.md)
