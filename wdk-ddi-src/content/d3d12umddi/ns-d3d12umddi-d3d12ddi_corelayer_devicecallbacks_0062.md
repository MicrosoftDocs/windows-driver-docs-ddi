---
UID: NS:d3d12umddi.D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
title: D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
author: windows-driver-content
description: Contains Microsoft Direct3D 12 runtime callback functions that the user-mode display driver can use.
tech.root: display
ms.assetid: f518bd61-c76b-4b46-94d5-6d1f2e664ce8
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_CORELAYER_DEVICECALLBACKS_0062 structure"]
ms.keywords: D3D12DDI_CORELAYER_DEVICECALLBACKS_0062, D3D12DDI_CORELAYER_DEVICECALLBACKS_0062,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2., 19H1
f1_keywords:
 - D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
 - d3d12umddi/D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_CORELAYER_DEVICECALLBACKS_0062
dev_langs:
 - c++
---

# D3D12DDI_CORELAYER_DEVICECALLBACKS_0062 structure


## -description

Contains Microsoft Direct3D 12 runtime callback functions that the user-mode display driver can use.

## -struct-fields

### -field pfnSetErrorCb

A pointer to the PFND3D12DDI_SETERROR_CB function.

### -field pfnSetCommandListErrorCb

A pointer to the PFND3D12DDI_SETCOMMANDLISTERROR_CB function.

### -field pfnSetCommandListDDITableCb

A pointer to the PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB function.

### -field pfnCreateContextCb

A pointer to the PFND3D12DDI_CREATECONTEXT_CB function.

### -field pfnCreateContextVirtualCb

A pointer to the PFND3D12DDI_CREATECONTEXTVIRTUAL_CB function.

Supported starting in WDDM 2.0.

### -field pfnReservedCreateContextVirtualCb

A function pointer for WDDM versions less than 2.0.

### -field pfnDestroyContextCb

A pointer to the PFND3D12DDI_DESTROYCONTEXT_CB function.

### -field pfnCreatePagingQueueCb

A pointer to the PFND3D12DDI_CREATEPAGINGQUEUE_CB function.

Supported starting in WDDM 2.0.

### -field pfnDestroyPagingQueueCb

A pointer to the PFND3D12DDI_DESTROYPAGINGQUEUE_CB function.

Supported starting in WDDM 2.0.

### -field pfnMakeResidentCb

A pointer to the PFND3D12DDI_MAKERESIDENT_CB function.

Supported starting in WDDM 2.0.

### -field pfnEvictCb

A pointer to the PFND3D12DDI_EVICT_CB function.

Supported starting in WDDM 2.0.

### -field pfnReclaimAllocations2Cb

A pointer to the PFND3D12DDI_RECLAIMALLOCATIONS2_CB function.

Supported starting in WDDM 2.0.

### -field pfnOfferAllocationsCb

A pointer to the PFND3D12DDI_OFFERALLOCATIONS_CB function.

Supported starting in WDDM 2.0.

### -field pfnReservedCreatePagingQueueCb

A function pointer for WDDM versions less than 2.0.

### -field pfnReservedDestroyPagingQueueCb

A function pointer for WDDM versions less than 2.0.

### -field pfnReservedMakeResidentCb

A function pointer for WDDM versions less than 2.0.

### -field pfnReservedEvictCb

A function pointer for WDDM versions less than 2.0.

### -field pfnReservedReclaimAllocations2Cb

A function pointer for WDDM versions less than 2.0.

### -field pfnReservedOfferAllocationsCb

 
A function pointer for WDDM versions less than 2.0.

### -field pfnAllocateCb

A pointer to the PFND3D12DDI_ALLOCATE_CB_0022 function.

### -field pfnDeallocateCb

A pointer to the PFND3D12DDI_DEALLOCATE_CB_0022 function.

### -field pfnCreateSchedulingGroupContextCb

A pointer to a PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXT_CB_0050 function.

Supported starting in WDDM 2.5.

### -field pfnCreateSchedulingGroupContextVirtualCb

A pointer to a PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 function.

Supported starting in WDDM 2.5.

### -field pfnCreateHwQueueCb

A pointer to a PFND3D12DDI_CREATEHWQUEUE_CB_0050 function.

Supported starting in WDDM 2.5.

### -field pfnReservedCreateSchedulingGroupContextCb

A function pointer for WDDM versions less than 2.5.

### -field pfnReservedCreateSchedulingGroupContextVirtualCb

A function pointer for WDDM versions less than 2.5.

### -field pfnReservedCreateHwQueueCb

A function pointer for WDDM versions less than 2.5.

### -field pfnQueueBackgroundProcessingWorkCb

A pointer to a PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062 function.

Supported starting in WDDM 2.6.

## -remarks

## -see-also

