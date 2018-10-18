---
UID: NS:d3d12umddi.D3D12DDI_CORELAYER_DEVICECALLBACKS_0050
title: D3D12DDI_CORELAYER_DEVICECALLBACKS_0050
author: windows-driver-content
description: The D3D12DDI_CORELAYER_DEVICECALLBACKS_0050 structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
ms.assetid: 92e47a76-7001-40e0-ba83-c01cf4fd1f9e
ms.date: 
ms.topic: struct
ms.keywords: D3D12DDI_CORELAYER_DEVICECALLBACKS_0050, D3D12DDI_CORELAYER_DEVICECALLBACKS_0050, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_CORELAYER_DEVICECALLBACKS_0050
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_CORELAYER_DEVICECALLBACKS_0050
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_CORELAYER_DEVICECALLBACKS_0050 structure

## -description

The D3D12DDI_CORELAYER_DEVICECALLBACKS_0050 structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.

## -struct-fields

### -field pfnSetErrorCb

A pointer to the pfnSetErrorCb function.


### -field pfnSetCommandListErrorCb

A pointer to the function.


### -field pfnSetCommandListDDITableCb

A pointer to the pfnSetCommandListErrorCb function.


### -field pfnCreateContextCb

A pointer to the pfnCreateContextCb function.


### -field pfnCreateContextVirtualCb

A pointer to the pfnCreateContextVirtualCb function.


### -field pfnDestroyContextCb

A pointer to the pfnDestroyContextCb function.


### -field pfnCreatePagingQueueCb

A pointer to the pfnCreatePagingQueueCb function.


### -field pfnDestroyPagingQueueCb

A pointer to the pfnDestroyPagingQueueCb function.


### -field pfnMakeResidentCb

A pointer to the pfnMakeResidentCb function.


### -field pfnEvictCb

A pointer to the pfnEvictCb function.


### -field pfnReclaimAllocations2Cb

A pointer to the pfnReclaimAllocations2Cb function.


### -field pfnOfferAllocationsCb

A pointer to the pfnOfferAllocationsCb function.


### -field pfnAllocateCb

Allocation callback function.


### -field pfnDeallocateCb

Deallocation callback function.

### -field pfnCreateSchedulingGroupContextCb

Create scheduling group context callback function.

### -field pfnCreateSchedulingGroupContextVirtualCb

Create scheduling group context virtual callback function.

### -field pfnCreateHwQueueCb
 
Create hardware queue callback function.

## -remarks

## -see-also
