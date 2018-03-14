---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB
author: windows-driver-content
description: pfnSignalSynchronizationObjectFromGpuCb is used to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromgpucb.htm
old-project: display
ms.assetid: 46F23D7A-5C7A-4BCC-A575-5D47F590B07C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB, d3dumddi/pfnSignalSynchronizationObjectFromGpuCb, display.pfnsignalsynchronizationobjectfromgpucb, pfnSignalSynchronizationObjectFromGpuCb, pfnSignalSynchronizationObjectFromGpuCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dumddi.h
api_name:
-	pfnSignalSynchronizationObjectFromGpuCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB callback


## -description


<b>pfnSignalSynchronizationObjectFromGpuCb</b> is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from a GPU packet using <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <b>pfnSignalSynchronizationObjectFromGpuCb</b>, as it supports all synchronization object types. 


## -prototype


````
PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB pfnSignalSynchronizationObjectFromGpuCb;

HRESULT APIENTRY CALLBACK* pfnSignalSynchronizationObjectFromGpuCb(
  _In_       HANDLE                                      hDevice,
  _In_ const D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</a> structure that provides the details of the requested operation.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function semantics are similar to existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> call. In addition, the function supports monitored fence objects and an array of monitored fence values to signal.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a>



<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</a>



 

 


