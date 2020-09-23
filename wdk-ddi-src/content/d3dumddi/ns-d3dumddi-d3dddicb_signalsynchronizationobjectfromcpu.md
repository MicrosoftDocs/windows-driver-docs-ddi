---
UID: NS:d3dumddi.D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU (d3dumddi.h)
description: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with pfnSignalSynchronizationObjectFromCpuCb to enable a driver to signal a monitored fence.
old-location: display\d3dddicb_signalsynchronizationobjectfromcpu.htm
tech.root: display
ms.assetid: 14CA5FD1-00CB-474B-A2A3-4264CAFA063A
ms.date: 05/10/2018
keywords: ["D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure"]
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, display.d3dddicb_signalsynchronizationobjectfromcpu
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
f1_keywords:
 - D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
 - d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
---

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure


## -description

<b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb">pfnSignalSynchronizationObjectFromCpuCb</a> to enable a driver to signal a monitored fence.

## -struct-fields

### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>.

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to signal.

### -field FenceValueArray

[in] An array of 64 bit monitored fence values to signal, each corresponding to an object in the <b>ObjectHandleArray</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb">pfnSignalSynchronizationObjectFromCpuCb</a>