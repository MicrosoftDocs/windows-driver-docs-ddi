---
UID: NF:ntddk.MmMapViewInSystemSpace
title: MmMapViewInSystemSpace function (ntddk.h)
description: The MmMapViewInSystemSpace function maps the specified section into the system's address space.
tech.root: kernel
ms.date: 10/19/2018
keywords: ["MmMapViewInSystemSpace function"]
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
req.irql: <=APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - MmMapViewInSystemSpace
 - ntddk/MmMapViewInSystemSpace
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - MmMapViewInSystemSpace
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

