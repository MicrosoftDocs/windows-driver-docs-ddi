---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
author: windows-driver-content
description: pfnSignalSynchronizationObjectFromGpu2Cb is used to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromgpu2cb.htm
old-project: display
ms.assetid: 03F9E47D-A3CA-44A1-A136-8236309D3D36
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB, d3dumddi/pfnSignalSynchronizationObjectFromGpu2Cb, display.pfnsignalsynchronizationobjectfromgpu2cb, pfnSignalSynchronizationObjectFromGpu2Cb, pfnSignalSynchronizationObjectFromGpu2Cb callback function [Display Devices]
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
-	pfnSignalSynchronizationObjectFromGpu2Cb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback


## -description


<b>pfnSignalSynchronizationObjectFromGpu2Cb</b> is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from the GPU packet using <b>pfnSignalSynchronizationObjectFromGpu2Cb</b>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a> and <a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <a href="https://msdn.microsoft.com/46F23D7A-5C7A-4BCC-A575-5D47F590B07C">pfnSignalSynchronizationObjectFromGpuCb</a>, as it supports all synchronization object types. 


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn701956">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a> structure that provides the details of the requested operation.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn701956">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a>



<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/46F23D7A-5C7A-4BCC-A575-5D47F590B07C">pfnSignalSynchronizationObjectFromGpuCb</a>
 

 

