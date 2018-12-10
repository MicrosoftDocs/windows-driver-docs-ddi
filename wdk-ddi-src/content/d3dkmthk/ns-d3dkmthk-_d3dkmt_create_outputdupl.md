---
UID: NS:d3dkmthk._D3DKMT_CREATE_OUTPUTDUPL
title: _D3DKMT_CREATE_OUTPUTDUPL
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
ms.assetid: c3d26e7c-7d05-4965-a725-8a9269c80a7c
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_CREATE_OUTPUTDUPL, D3DKMT_CREATE_OUTPUTDUPL, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_CREATE_OUTPUTDUPL
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_CREATE_OUTPUTDUPL
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DKMT_CREATE_OUTPUTDUPL structure

## -description

Reserved for system use. Do not use in your driver.

## -struct-fields

### -field hAdapter

A handle to the display adapter.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display mode applies to.

### -field KeyedMutexCount

[in] The number of keyed mutexs. If zero, then this the pre-create check.

### -field RequiredKeyedMutexCount

[out] The number of keyed mutexs needed.

### -field KeyedMutexs

Pointer to an array of keyed mutexs.

### -field Flags
 
Flags required to create the structure.

## -remarks

## -see-also
