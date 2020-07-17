---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB (d3dumddi.h)
description: pfnWaitForSynchronizationObjectFromGpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromgpucb.htm
tech.root: display
ms.assetid: 49023D25-D57E-418F-AD10-133377B90493
ms.date: 05/10/2018
keywords: ["PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback function"]
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback, d3dumddi/pfnWaitForSynchronizationObjectFromGpuCb, display.pfnwaitforsynchronizationobjectfromgpucb, pfnWaitForSynchronizationObjectFromGpuCb, pfnWaitForSynchronizationObjectFromGpuCb callback function [Display Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnWaitForSynchronizationObjectFromGpuCb"
 - "pfnWaitForSynchronizationObjectFromGpuCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnWaitForSynchronizationObjectFromGpuCb
product:
 - Windows
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback function

## -description

<b>pfnWaitForSynchronizationObjectFromGpuCb</b> waits for a monitored fence to reach a certain value before processing subsequent context commands. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <b>pfnWaitForSynchronizationObjectFromGpuCb</b>, as it supports all synchronization object types.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromgpu">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a> structure that provides the details of the requested operation.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

This function semantics are similar to existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb">pfnWaitForSynchronizationObject2Cb</a> call, except that this callback also supports monitored fence objects and an array of monitored fence values to wait for.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromgpu">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a>



<i>pfnWaitForSynchronizationObject2Cb</i>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a>

