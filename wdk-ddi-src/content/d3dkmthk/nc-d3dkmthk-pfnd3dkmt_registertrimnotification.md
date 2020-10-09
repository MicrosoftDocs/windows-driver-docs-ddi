---
UID: NC:d3dkmthk.PFND3DKMT_REGISTERTRIMNOTIFICATION
title: PFND3DKMT_REGISTERTRIMNOTIFICATION (d3dkmthk.h)
description: The PFND3DKMT_REGISTERTRIMNOTIFICATION callback function registers trim notifications.
ms.assetid: 149ad603-b237-4f6b-b185-be4a0a9590d2
ms.date: 10/19/2018
keywords: ["PFND3DKMT_REGISTERTRIMNOTIFICATION callback function"]
req.header: d3dkmthk.h
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
tech.root: display
f1_keywords:
 - PFND3DKMT_REGISTERTRIMNOTIFICATION
 - d3dkmthk/PFND3DKMT_REGISTERTRIMNOTIFICATION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_REGISTERTRIMNOTIFICATION
dev_langs:
 - c++
---

# PFND3DKMT_REGISTERTRIMNOTIFICATION callback function


## -description

The PFND3DKMT_REGISTERTRIMNOTIFICATION callback function registers trim notifications.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_REGISTERTRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_registertrimnotification.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_REGISTERTRIMNOTIFICATION Pfnd3dkmtRegistertrimnotification; 

// Definition

NTSTATUS Pfnd3dkmtRegistertrimnotification 
(
	D3DKMT_REGISTERTRIMNOTIFICATION *
)
{...}

```

## -remarks

## -see-also

