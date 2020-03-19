---
UID: NC:d3dkmddi.DXGKCB_MAPFRAMEBUFFERPOINTER
title: DXGKCB_MAPFRAMEBUFFERPOINTER (d3dkmddi.h)
description: Implemented by the client driver to obtain a pointer to a subregion of the section object that was created for each physical adapter.
ms.assetid: 86a95724-5522-4075-a1c6-9c0ccfe1193e
ms.date: 10/19/2018
keywords: ["DXGKCB_MAPFRAMEBUFFERPOINTER callback function"]
f1_keywords:
 - "d3dkmddi/DXGKCB_MAPFRAMEBUFFERPOINTER"
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
- DXGKCB_MAPFRAMEBUFFERPOINTER
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_MAPFRAMEBUFFERPOINTER callback function

## -description

Implemented by the client driver to obtain a pointer to a subregion of the section object that was created for each physical adapter. The driver is responsible for copying the data from the pre-allocated buffer to the mapped subregion.

## -prototype

```cpp
//Declaration

DXGKCB_MAPFRAMEBUFFERPOINTER DxgkcbMapframebufferpointer;

// Definition

NTSTATUS DxgkcbMapframebufferpointer
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARGCB_MAPFRAMEBUFFERPOINTER pMapFrameBufferPointer
)
{...}

DXGKCB_MAPFRAMEBUFFERPOINTER


```

## -parameters

### -param hAdapter

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pMapFrameBufferPointer

Pointer to [DXGKARGCB_MAPFRAMEBUFFERPOINTER](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) structure that contains a pointer to the subregion of the section object.

## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [DXGKARGCB_MAPFRAMEBUFFERPOINTER](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) and then calling DxgkCbMapFrameBufferPointer.

For drivers that must save reserved portions of the frame buffer to system memory during power transitions, Windows graphics port driver (Dxgkrnl) will take a commit charge on required memory at initialization time for the adapter. This will be queried through [QueryAdapterInfo](nc-d3dkmddi-dxgkddi_queryadapterinfo.md). If the driver reports IoMmu isolation support, Dxgkrnl will take a commit charge on the amount specified by the driver to ensure that it can always get physical pages upon request. This is done by creating a unique section object for each physical adapter which specifies a non-zero value for the maximum size. The maximum size reported by the driver must be a multiple of PAGE_SIZE.

Performing the transfer to and from the frame buffer can be done at a time of the driver’s choice. Dxgkrnl provides callbacks that are used to map the appropriate portions of the section object, which was created when the adapter was initialized.

When calling the DxgkCbPinFrameBufferForSave, DxgkCbUnpinFrameBufferForSave, DxgkcbMapframebufferpointer/DxgkCbUnmapFrameBufferPointer callback functions, the driver must always provide the *hAdapter* for the master/lead device in an LDA chain.

The driver has two options to implement the frame buffer reservation:

1. (Preferred method) The driver should allocate space per physical adapter using the above QueryAdapterInfo call to specify the amount of storage that is needed per adapter. At the time of the power transition, the driver should save or restore the memory one physical adapter at a time. This memory will be split across multiple section objects, one per physical adapter.

2. Optionally, the driver can save or restore all data into a single shared section object. This can be done by specifying a single large maximum size in the QueryAdapterInfo call for physical adapter 0, and then a zero value for all other physical adapters. The driver may then pin down the entire section object once for use across all save/restore operations, for all of the physical adapters. This method has the primary drawback that it requires locking a larger amount of memory at once, since it does not support pinning only a subrange of the memory into an MDL. As a result, this operation is more likely to fail under memory pressure. The driver would also be expected to map the pages in the MDL to the GPU using the correct page offsets.

If pinning the entire frame buffer’s section object fails, the driver must try to ensure forward progress by performing the transfer in smaller pieces. This is accomplished by allocating a small MDL or chunk of memory during initialization time which can be used to transfer the contents from the hardware. Then call DxgkCbMapFrameBufferPointer to obtain a pointer to a subregion of the section object. The driver is responsible for copying the data from the pre-allocated buffer to the mapped subregion. The reverse is true when restoring the frame buffer contents.

## -see-also
