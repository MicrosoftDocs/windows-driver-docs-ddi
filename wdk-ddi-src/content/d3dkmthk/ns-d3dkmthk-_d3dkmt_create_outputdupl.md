---
UID: NS:d3dkmthk._D3DKMT_CREATE_OUTPUTDUPL
title: _D3DKMT_CREATE_OUTPUTDUPL (d3dkmthk.h)
description: "Microsoft reserves the D3DKMT_CREATE_OUTPUTDUPL structure for internal use only. Don't use this structure in your driver."
ms.date: 10/19/2018
keywords: ["D3DKMT_CREATE_OUTPUTDUPL structure"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_CREATE_OUTPUTDUPL
 - d3dkmthk/_D3DKMT_CREATE_OUTPUTDUPL
 - D3DKMT_CREATE_OUTPUTDUPL
 - d3dkmthk/D3DKMT_CREATE_OUTPUTDUPL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATE_OUTPUTDUPL
 - D3DKMT_CREATE_OUTPUTDUPL
dev_langs:
 - c++
---

# _D3DKMT_CREATE_OUTPUTDUPL structure


## -description

Reserved for system use. Do not use in your driver.

## -struct-fields

### -field hAdapter

A handle to the display adapter.

### -field VidPnSourceId [in]

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display mode applies to.

### -field KeyedMutexCount [in]

The number of keyed mutexs. If zero, then this the pre-create check.

### -field RequiredKeyedMutexCount [out]

The number of keyed mutexs needed.

### -field KeyedMutexs

Pointer to an array of keyed mutexs.

### -field Flags

 
Flags required to create the structure.

## -remarks

## -see-also

