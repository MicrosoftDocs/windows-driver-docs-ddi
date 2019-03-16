---
UID: NC:d3dkmddi.DXGKCB_UNPINFRAMEBUFFERFORSAVE
title: DXGKCB_UNPINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: Implemented by the client driver to release the mapping that was set by DXGKCB_PINFRAMEBUFFERFORSAVE.
ms.assetid: 403a4aea-21e8-4a97-8314-c85bac6555ef
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKCB_UNPINFRAMEBUFFERFORSAVE
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function

## -description

Implemented by the client driver to release the mapping that was set by [DXGKCB_PINFRAMEBUFFERFORSAVE](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md).

## -prototype

```cpp
//Declaration

DXGKCB_UNPINFRAMEBUFFERFORSAVE DxgkcbUnpinframebufferforsave;

// Definition

NTSTATUS DxgkcbUnpinframebufferforsave
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARGCB_UNPINFRAMEBUFFERFORSAVE pUnpinFrameBufferForSave
)
{...}

DXGKCB_UNPINFRAMEBUFFERFORSAVE


```

## -parameters

### -param hAdapter

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pUnpinFrameBufferForSave:

A pointer to the [DXGKARGCB_UNPINFRAMEBUFFERFORSAVE](ns-d3dkmddi-_dxgkargcb_unpinframebufferforsave.md) structure that contains a handle to the memory to be unmapped.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARGCB_UNPINFRAMEBUFFERFORSAVE and then calling DxgkCbUnpinFrameBufferForSave.


## -see-also
