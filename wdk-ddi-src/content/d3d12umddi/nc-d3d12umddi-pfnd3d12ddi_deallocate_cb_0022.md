---
UID: NC:d3d12umddi.PFND3D12DDI_DEALLOCATE_CB_0022
title: PFND3D12DDI_DEALLOCATE_CB_0022
author: windows-driver-content
description: The pfnDeallocateCb callback function controls heap deallocation by using a D3D12DDICB_DEALLOCATE_0022 structure.
old-location: display\pfnd3d12ddi_deallocate_cb_0022.htm
old-project: display
ms.assetid: 85304F27-A522-44B7-86EC-31F670828354
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D12DDI_DEALLOCATE_CB_0022, PFND3D12DDI_DEALLOCATE_CB_0022 callback, d3d12umddi/pfnDeallocateCb, display.pfnd3d12ddi_deallocate_cb_0022, pfnDeallocateCb, pfnDeallocateCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnDeallocateCb
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D12DDI_DEALLOCATE_CB_0022 callback function


## -description


The <i>pfnDeallocateCb</i> callback function controls heap deallocation by using a <a href="https://msdn.microsoft.com/977868D1-02E1-4460-9194-2079B986045E">D3D12DDICB_DEALLOCATE_0022</a> structure.


## -parameters




### -param Arg1


### -param *








#### - Deallocate [in]

A  <a href="https://msdn.microsoft.com/977868D1-02E1-4460-9194-2079B986045E">D3D12DDICB_DEALLOCATE_0022</a> structure that contains information for a deallocation.


#### - hRTDevice [in]

The handle for a device.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this callback function by using the <a href="https://msdn.microsoft.com/E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.




## -see-also




<a href="https://msdn.microsoft.com/977868D1-02E1-4460-9194-2079B986045E">D3D12DDICB_DEALLOCATE_0022</a>



<a href="https://msdn.microsoft.com/E5B7FDB6-3351-489E-B0BB-8B8DD605FCF4">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



<a href="https://msdn.microsoft.com/D0326C98-F187-4F62-AE60-60F0B38AB0D4">pfnAllocateCb</a>
 

 

