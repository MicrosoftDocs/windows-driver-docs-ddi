---
UID: NS:d3d12umddi.D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
title: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
author: windows-driver-content
description: This structure contains runtime callback functions that the user-mode display driver can use.
old-location: display\d3d12ddi_corelayer_devicecallbacks_0022.htm
old-project: display
ms.assetid: E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022, D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure [Display Devices], d3d12umddi/D3D12DDI_CORELAYER_DEVICECALLBACKS_0022, display.d3d12ddi_corelayer_devicecallbacks_0022
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CORELAYER_DEVICECALLBACKS_0022
---

# D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure


## -description


This structure contains runtime callback functions that the user-mode display driver can use.


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

A pointer to the <a href="https://msdn.microsoft.com/D0326C98-F187-4F62-AE60-60F0B38AB0D4">pfnAllocateCb</a> function.


### -field pfnDeallocateCb

A pointer to the <a href="https://msdn.microsoft.com/85304F27-A522-44B7-86EC-31F670828354">pfnDeallocateCb</a> function.

