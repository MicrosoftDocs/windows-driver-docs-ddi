---
UID: NC:d3dkmthk.PFND3DKMT_UNPINDIRECTFLIPRESOURCES
title: PFND3DKMT_UNPINDIRECTFLIPRESOURCES (d3dkmthk.h)
description: The PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function unpins direct flip resources.
ms.assetid: 4b2692d3-7747-490e-9f90-45f8d4cfbf72
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_UNPINDIRECTFLIPRESOURCES"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- PFND3DKMT_UNPINDIRECTFLIPRESOURCES
- D3DKMTUnpinDirectFlipResources
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function

## -description

The PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function unpins direct flip resources.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNPINDIRECTFLIPRESOURCES D3DKMTUnpinDirectFlipResources;

_Check_return_ NTSTATUS APIENTRY* D3DKMTUnpinDirectFlipResources(
  _In_ const D3DKMT_UNPINDIRECTFLIPRESOURCES *pResources
)
{ ... }

```

## -parameters

### -param Arg1

*\_In\_* *pResources*

Pointer to a [D3DKMT_UNPINDIRECTFLIPRESOURCES](ns-d3dkmthk-_d3dkmt_unpindirectflipresources.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also

[D3DKMT_UNPINDIRECTFLIPRESOURCES](ns-d3dkmthk-_d3dkmt_unpindirectflipresources.md)
