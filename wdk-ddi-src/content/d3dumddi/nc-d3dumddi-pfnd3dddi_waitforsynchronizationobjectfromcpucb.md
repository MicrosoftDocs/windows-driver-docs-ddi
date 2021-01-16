---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB (d3dumddi.h)
description: pfnWaitForSynchronizationObjectFromCpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromcpucb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB callback function"]
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB callback, d3dumddi/pfnWaitForSynchronizationObjectFromCpuCb, display.pfnwaitforsynchronizationobjectfromcpucb, pfnWaitForSynchronizationObjectFromCpuCb, pfnWaitForSynchronizationObjectFromCpuCb callback function [Display Devices]
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
 - PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
 - d3dumddi/PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
product:
 - Windows
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB callback function


## -description

The **pfnWaitForSynchronizationObjectFromCpuCb** callback waits for a monitored fence to reach a certain value before processing subsequent context commands.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

Pointer to a [**D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMCPU**](ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromcpu.md) structure that provides the details of the requested operation.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

