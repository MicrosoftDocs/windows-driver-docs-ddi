---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB
author: windows-driver-content
description: pfnSignalSynchronizationObjectFromGpuCb is used to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromgpucb.htm
old-project: display
ms.assetid: 46F23D7A-5C7A-4BCC-A575-5D47F590B07C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnsignalsynchronizationobjectfromgpucb, pfnSignalSynchronizationObjectFromGpuCb callback function [Display Devices], pfnSignalSynchronizationObjectFromGpuCb, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB, d3dumddi/pfnSignalSynchronizationObjectFromGpuCb
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3dumddi.h
apiname: 
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

<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

