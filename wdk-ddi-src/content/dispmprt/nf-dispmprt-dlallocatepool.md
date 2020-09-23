---
UID: NF:dispmprt.DlAllocatePool
title: DlAllocatePool function
description: Allocates pool memory of the specified type.
tech.root: display
ms.assetid: 89dbd943-dc4d-489b-96ed-0486536903cf
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlAllocatePool function"]
ms.keywords: DlAllocatePool
req.header: dispmprt.h
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
ms.custom: 19H1
f1_keywords:
 - DlAllocatePool
 - dispmprt/DlAllocatePool
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlAllocatePool
product:
 - Windows
dev_langs:
 - c++
---

# DlAllocatePool function


## -description

Allocates pool memory of the specified type.

## -parameters

### -param DeviceHandle

A handle to the device.

### -param PoolType

Specifies the type of pool memory to allocate.

### -param NumberOfBytes

Specifies the number of bytes to allocate.

### -param Tag

## -returns

This function returns PVOID.

## -remarks

## -see-also

