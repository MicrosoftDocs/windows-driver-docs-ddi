---
UID: NC:d3dkmthk.PFND3DKMT_UNREGISTERTRIMNOTIFICATION
title: PFND3DKMT_UNREGISTERTRIMNOTIFICATION (d3dkmthk.h)
description: PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
ms.assetid: 3e329473-b630-4e29-ace3-7ae0c2606198
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_UNREGISTERTRIMNOTIFICATION"
 - "PFND3DKMT_UNREGISTERTRIMNOTIFICATION"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_UNREGISTERTRIMNOTIFICATION
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function

## -description

PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).

## -prototype

```cpp
//Declaration

PFND3DKMT_UNREGISTERTRIMNOTIFICATION Pfnd3dkmtUnregistertrimnotification; 

// Definition

NTSTATUS Pfnd3dkmtUnregistertrimnotification 
(
	D3DKMT_UNREGISTERTRIMNOTIFICATION *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_UNREGISTERTRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
