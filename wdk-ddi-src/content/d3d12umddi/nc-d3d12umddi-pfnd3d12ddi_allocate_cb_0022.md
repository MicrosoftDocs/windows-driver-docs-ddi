---
UID: NC:d3d12umddi.PFND3D12DDI_ALLOCATE_CB_0022
title: PFND3D12DDI_ALLOCATE_CB_0022 (d3d12umddi.h)
description: The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value.
old-location: display\pfnd3d12ddi_allocate_cb_0022.htm
ms.assetid: D0326C98-F187-4F62-AE60-60F0B38AB0D4
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_ALLOCATE_CB_0022, PFND3D12DDI_ALLOCATE_CB_0022 callback, d3d12umddi/pfnAllocateCb, display.pfnd3d12ddi_allocate_cb_0022, pfnAllocateCb, pfnAllocateCb callback function [Display Devices]
ms.topic: callback
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnAllocateCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_ALLOCATE_CB_0022 callback function


## -description


The <i>pfnAllocateCb</i> callback function controls heap allocation by using a <a href="https://msdn.microsoft.com/C39262BA-D1CE-4634-974A-ACCE8D321830">D3D12DDICB_ALLOCATE_0022</a> value.


## -parameters




### -param Arg1

The handle for a device.

### -param *


A <a href="https://msdn.microsoft.com/C39262BA-D1CE-4634-974A-ACCE8D321830">D3D12DDICB_ALLOCATE_0022</a> structure that contains information for an allocation.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this callback function by using the <a href="https://msdn.microsoft.com/E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.




## -see-also




<a href="https://msdn.microsoft.com/C39262BA-D1CE-4634-974A-ACCE8D321830">D3D12DDICB_ALLOCATE_0022</a>



<a href="https://msdn.microsoft.com/E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



<a href="https://msdn.microsoft.com/85304F27-A522-44B7-86EC-31F670828354">pfnDeallocateCb</a>
 

 

