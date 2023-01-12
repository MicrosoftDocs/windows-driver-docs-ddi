---
UID: NF:acxmanager.AcxGetManager
tech.root: audio
title: AcxGetManager
ms.date: 12/16/2022
targetos: Windows
description: The AcxGetManager function returns the underlying ACXMANAGER handle.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxmanager.h
api_name:
 - AcxGetManager
f1_keywords:
 - AcxGetManager
 - acxmanager/AcxGetManager
dev_langs:
 - c++
---

## -description

The **AcxGetManager** function returns the underlying ACXMANAGER handle.

## -parameters

### -param Context [in]

Reserved, set this to `NULL`.

## -returns

Returns the underlying ACXMANAGER handle.

## -remarks

The *Context* parameter must be set to `NULL`.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmanager.h header](index.md)
