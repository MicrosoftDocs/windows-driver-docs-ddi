---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB (d3dumddi.h)
description: pfnSignalSynchronizationObjectFromCpuCb enables a driver to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromcpucb.htm
tech.root: display
ms.assetid: E6FD5215-09CE-4DC8-B5AB-F65E68E2A884
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB callback, d3dumddi/pfnSignalSynchronizationObjectFromCpuCb, display.pfnsignalsynchronizationobjectfromcpucb, pfnSignalSynchronizationObjectFromCpuCb, pfnSignalSynchronizationObjectFromCpuCb callback function [Display Devices]
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
 - "d3dumddi/pfnSignalSynchronizationObjectFromCpuCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnSignalSynchronizationObjectFromCpuCb
product:
 - Windows
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB callback function

## -description

<b>pfnSignalSynchronizationObjectFromCpuCb</b> enables a driver to signal a monitored fence.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromcpu">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</a> structure that provides the details of the requested operation.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

When a monitored fence object is signaled by the CPU, the graphics kernel will update the fence memory location with the signaled value, so it becomes immediately visible to any user mode reader as well as immediately un-wait any satisfied waiters.
However, the caller cannot assume that the signal operation will be completed upon the return from this function. Instead, the caller should use appropriate <i>Wait</i> functions to check for signal completion.


<div class="alert"><b>Note</b>  A signal from a graphics processing unit (GPU) call is not provided. Instead, a driver can signal a new fence value by inserting a GPU write command for <b>FenceValueGPUVirtualAddress</b> into a command buffer.
</div>
<div> </div>

