---
UID: NS:d3d12umddi.D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
title: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 (d3d12umddi.h)
description: This structure contains runtime callback functions that the user-mode display driver can use.
old-location: display\d3d12ddi_corelayer_devicecallbacks_0022.htm
ms.assetid: E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4
ms.date: 05/10/2018
ms.keywords: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022, D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure [Display Devices], d3d12umddi/D3D12DDI_CORELAYER_DEVICECALLBACKS_0022, display.d3d12ddi_corelayer_devicecallbacks_0022
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
ms.custom: 19H1
---

# D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure


## -description


This structure contains runtime callback functions that the user-mode display driver can use.


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

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022">pfnAllocateCb</a> function.


### -field pfnDeallocateCb

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022">pfnDeallocateCb</a> function.

