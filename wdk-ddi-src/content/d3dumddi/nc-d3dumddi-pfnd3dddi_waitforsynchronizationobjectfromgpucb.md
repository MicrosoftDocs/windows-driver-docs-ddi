---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB
author: windows-driver-content
description: pfnWaitForSynchronizationObjectFromGpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromgpucb.htm
old-project: display
ms.assetid: 49023D25-D57E-418F-AD10-133377B90493
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB, d3dumddi/pfnWaitForSynchronizationObjectFromGpuCb, display.pfnwaitforsynchronizationobjectfromgpucb, pfnWaitForSynchronizationObjectFromGpuCb, pfnWaitForSynchronizationObjectFromGpuCb callback function [Display Devices]
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
-	pfnWaitForSynchronizationObjectFromGpuCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback


## -description


<b>pfnWaitForSynchronizationObjectFromGpuCb</b> waits for a monitored fence to reach a certain value before processing subsequent context commands. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <b>pfnWaitForSynchronizationObjectFromGpuCb</b>, as it supports all synchronization object types.


## -prototype


````
PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB pfnWaitForSynchronizationObjectFromGpuCb;

HRESULT APIENTRY CALLBACK* pfnWaitForSynchronizationObjectFromGpuCb(
  _In_       HANDLE                                        hDevice,
  _In_ const  D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromgpu.md">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a> structure that provides the details of the requested operation.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function semantics are similar to existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> call, except that this callback also supports monitored fence objects and an array of monitored fence values to wait for.




## -see-also

<i>pfnWaitForSynchronizationObject2Cb</i>



<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromgpu.md">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

