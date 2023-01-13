---
UID: NC:wdm.PBUILD_MDL_FROM_SCATTER_GATHER_LIST
title: PBUILD_MDL_FROM_SCATTER_GATHER_LIST (wdm.h)
description: The BuildMdlFromScatterGatherList routine builds an MDL from a scatter/gather list allocated by the system.Note  This routine is reserved for system use.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback function"]
ms.keywords: BuildMdlFromScatterGatherList, BuildMdlFromScatterGatherList callback function [Kernel-Mode Driver Architecture], PBUILD_MDL_FROM_SCATTER_GATHER_LIST, PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback, kdma_8a1b5bc2-b0ff-41ca-b352-647a0e7b4a79.xml, kernel.buildmdlfromscattergatherlist, wdm/BuildMdlFromScatterGatherList
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PBUILD_MDL_FROM_SCATTER_GATHER_LIST
 - wdm/PBUILD_MDL_FROM_SCATTER_GATHER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PBUILD_MDL_FROM_SCATTER_GATHER_LIST
---

## -description

The **BuildMdlFromScatterGatherList** routine builds an MDL from a scatter/gather list allocated by the system.

This routine is reserved for system use.

## -parameters

### -param DmaAdapter [in]

Pointer to the [**DMA_ADAPTER**](./ns-wdm-_dma_adapter.md) structure returned by [IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md) that represents the bus-master adapter or DMA controller.

### -param ScatterGather [in]

Pointer to the [**SCATTER_GATHER_LIST**](./ns-wdm-_scatter_gather_list.md) structure passed to the driver's [AdapterListControl](./nc-wdm-driver_list_control.md) routine.

### -param OriginalMdl [in]

Pointer to the original MDL that the driver used to build the scatter/gather list.

### -param TargetMdl [out]

Pointer to a variable the routine uses to return the MDL created to hold the buffer described by the scatter/gather list. The value returned can be the same as *OriginalMdl*.

## -returns

**BuildMdlFromScatterGatherList** returns one of the following status codes:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The operation succeeded. |
| **STATUS_INVALID_PARAMETER** | The *OriginalMdl* parameter is **NULL**. |
| **STATUS_INSUFFICIENT_RESOURCES** | There is not enough memory available to allocate a new MDL. |
| **STATUS_NONE_MAPPED** | The system has already created a new MDL for the memory locations in the scatter/gather list. (This only happens if the routine is called twice on the same scatter/gather list.) |

## -remarks

**BuildMdlFromScatterGatherList** is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a [**DMA_OPERATIONS**](./ns-wdm-_dma_operations.md) structure. Drivers obtain the address of this routine by calling [IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md) with the **Version** member of the *DeviceDescription* parameter set to DEVICE_DESCRIPTION_VERSION2. If **IoGetDmaAdapter** returns **NULL**, the routine is not available on your platform.

When a driver creates a scatter/gather list to write to a device, the system can make a copy of the data to be written, and use that copy to perform the DMA operation. Use this routine to access the memory locations in the scatter/gather list, regardless of whether those locations are a copy.

## -see-also

[BuildScatterGatherList](./nc-wdm-pbuild_scatter_gather_list.md)

[**DEVICE_DESCRIPTION**](./ns-wdm-_device_description.md)

[**DMA_ADAPTER**](./ns-wdm-_dma_adapter.md)

[**DMA_OPERATIONS**](./ns-wdm-_dma_operations.md)

[IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md)

[**SCATTER_GATHER_LIST**](./ns-wdm-_scatter_gather_list.md)