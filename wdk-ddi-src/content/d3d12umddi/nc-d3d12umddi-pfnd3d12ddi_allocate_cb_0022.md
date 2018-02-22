---
UID: NC:d3d12umddi.PFND3D12DDI_ALLOCATE_CB_0022
title: PFND3D12DDI_ALLOCATE_CB_0022
author: windows-driver-content
description: The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value.
old-location: display\pfnd3d12ddi_allocate_cb_0022.htm
old-project: display
ms.assetid: D0326C98-F187-4F62-AE60-60F0B38AB0D4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_allocate_cb_0022, pfnAllocateCb callback function [Display Devices], pfnAllocateCb, PFND3D12DDI_ALLOCATE_CB_0022, PFND3D12DDI_ALLOCATE_CB_0022, d3d12umddi/pfnAllocateCb
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnAllocateCb
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_ALLOCATE_CB_0022 callback


## -description


The <i>pfnAllocateCb</i> callback function controls heap allocation by using a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_allocate_0022.md">D3D12DDICB_ALLOCATE_0022</a> value.


## -prototype


````
PFND3D12DDI_ALLOCATE_CB_0022 pfnAllocateCb;

HRESULT APIENTRY CALLBACK* pfnAllocateCb(
  _In_    D3D12DDI_HRTDEVICE       hRTDevice,
  _Inout_ D3D12DDICB_ALLOCATE_0022 *Allocate
)
{ ... }
````


## -parameters




### -param D3D12DDI_HRTDEVICE


### -param *








#### - Allocate [in, out]

A <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_allocate_0022.md">D3D12DDICB_ALLOCATE_0022</a> structure that contains information for an allocation.


#### - hRTDevice [in]

The handle for a device.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this callback function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.




## -see-also

<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md">pfnDeallocateCb</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_allocate_0022.md">D3D12DDICB_ALLOCATE_0022</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_ALLOCATE_CB_0022 callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

