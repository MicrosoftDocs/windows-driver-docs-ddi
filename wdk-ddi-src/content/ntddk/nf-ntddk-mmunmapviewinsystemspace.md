---
UID: NF:ntddk.MmUnmapViewInSystemSpace
title: MmUnmapViewInSystemSpace function (ntddk.h)
description: "Learn more about: MmUnmapViewInSystemSpace function"
tech.root: kernel
ms.date: 10/19/2018
keywords: ["MmUnmapViewInSystemSpace function"]
ms.keywords: MmUnmapViewInSystemSpace
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <=(APC_LEVEL)
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
 - MmUnmapViewInSystemSpace
 - ntddk/MmUnmapViewInSystemSpace
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - MmUnmapViewInSystemSpace
---

# MmUnmapViewInSystemSpace function


## -description

 The MmUnmapViewInSystemSpace function unmaps the specified section from the system's address space.

## -parameters

### -param MappedBase

Supplies the address of the view to unmap.

## -returns

This function returns true if the map view operation was successful.

## -remarks

## -see-also

[MmMapViewInSystemSpace](nf-ntddk-mmmapviewinsystemspace.md)

