---
UID: NF:sensorsutils.InitPropVariantFromCLSIDArray
title: InitPropVariantFromCLSIDArray function (sensorsutils.h)
description: This routine initializes a PROPVARIANT from a given array of GUIDs.
ms.date: 08/08/2018
keywords: ["InitPropVariantFromCLSIDArray function"]
tech.root: sensors
ms.keywords: InitPropVariantFromCLSIDArray
req.header: sensorsutils.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
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
 - InitPropVariantFromCLSIDArray
 - sensorsutils/InitPropVariantFromCLSIDArray
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - InitPropVariantFromCLSIDArray
---

# InitPropVariantFromCLSIDArray function


## -description

This routine initializes a PROPVARIANT from a given array of GUIDs. The routine takes care of allocating memory for the CLSID array using CoTaskMemAlloc.

## -parameters

### -param members

[in] Array of GUIDs to initialize PROPVARIANT value.

### -param size

[in] Size of array of GUIDs being sent in.

### -param ppropvar

[out] Pointer to a PROPVARIANT.

## -returns

This function returns S_OK if the PROPVARIANT was properly initialized, E_OUTOFMEMORY if there was not enough memory to allocate the CLSID array in *ppropvar*.

## -remarks

## -see-also

