---
UID: NF:ntddk.PsGetSiloContainerId
title: PsGetSiloContainerId function (ntddk.h)
description: Gets the ContainerId for the given Silo.
tech.root: kernel
ms.assetid: ba43355c-380c-46a8-85e7-bae024683744
ms.date: 09/30/2018
tech.root: kernel
keywords: ["PsGetSiloContainerId function"]
ms.keywords: PsGetSiloContainerId
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
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
 - PsGetSiloContainerId
 - ntddk/PsGetSiloContainerId
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PsGetSiloContainerId
---

# PsGetSiloContainerId function


## -description

Gets the ContainerId for the given Silo.

## -parameters

### -param Silo

[in] A pointer to the Silo being queried.

## -returns

Returns the GUID identifier for the silo.

## -remarks

## -see-also

