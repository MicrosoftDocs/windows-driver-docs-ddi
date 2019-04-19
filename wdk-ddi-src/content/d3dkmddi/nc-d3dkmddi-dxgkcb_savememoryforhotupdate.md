---
UID: NC:d3dkmddi.DXGKCB_SAVEMEMORYFORHOTUPDATE
title: DXGKCB_SAVEMEMORYFORHOTUPDATE
author: windows-driver-content
description: Implemented by the client driver to save adapter memory to support driver hot update.
tech.root: display
ms.assetid: 5ce7e415-c589-4d8e-b53a-d4bc8625f9c1
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= APC_LEVEL
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
 - DXGKCB_SAVEMEMORYFORHOTUPDATE
product:
- Windows
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGKCB_SAVEMEMORYFORHOTUPDATE callback function

## -description

Implemented by the client driver to save adapter memory to support driver hot update.

## -prototype

```
//Declaration

DXGKCB_SAVEMEMORYFORHOTUPDATE DxgkcbSavememoryforhotupdate; 

// Definition

NTSTATUS DxgkcbSavememoryforhotupdate 
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARGCB_SAVEMEMORYFORHOTUPDATE pArgs
)
{...}

```

## -parameters

### -param hAdapter

[in] A handle to the DXGK adapter that is passed to [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md).

### -param pArgs

[in] A pointer to the [DXGKARGCB_SAVEMEMORYFORHOTUPDATE](ns-d3dkmddi-dxgkargcb_savememoryforhotupdate.md) structure that contains arguments for this callback.

## -returns

Returns STATUS_SUCCESS if the operation succeeds.

## -remarks

Each call to **DxgkCbSaveMemoryForHotUpdate** saves a block of physical memory pages and optionally metadata, which the driver wants to associate with the memory block. When the pages are restored, the driver will get a separate call for each saved memory block together with metadata.

For convenience, the callback provides 3 options to save physical memory:

* As an array of contiguous physical memory ranges  (*pDataMemoryRanges*)
* As an MDL (*pDataMdl*)
* As virtual memory buffer (*pData*)

One (and only one) of the pointers to data (pDataMemoryRanges, pDataMdl or pData) must be not NULL.

## -see-also
