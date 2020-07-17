---
UID: NS:d3d12umddi.D3D12DDI_CORELAYER_DEVICECALLBACKS_0003
title: D3D12DDI_CORELAYER_DEVICECALLBACKS_0003
author: windows-driver-content
description: Contains Microsoft Direct3D 12 runtime callback functions that the user-mode display driver can use.
tech.root: display
ms.assetid: a8959163-9639-4c75-aeb1-5aabad140a42
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_CORELAYER_DEVICECALLBACKS_0003"
 - "D3D12DDI_CORELAYER_DEVICECALLBACKS_0003"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_CORELAYER_DEVICECALLBACKS_0003, D3D12DDI_CORELAYER_DEVICECALLBACKS_0003, 
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
req.typenames: D3D12DDI_CORELAYER_DEVICECALLBACKS_0003
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_CORELAYER_DEVICECALLBACKS_0003
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 structure

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

## -remarks

## -see-also
