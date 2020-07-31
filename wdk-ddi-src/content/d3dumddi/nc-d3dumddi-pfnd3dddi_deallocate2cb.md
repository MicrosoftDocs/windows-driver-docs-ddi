---
UID: NC:d3dumddi.PFND3DDDI_DEALLOCATE2CB
title: PFND3DDDI_DEALLOCATE2CB (d3dumddi.h)
description: The pfnDeallocate2Cb user mode callback function releases allocations for a kernel-mode resource object if the resource object was created.
old-location: display\pfndeallocate2cb.htm
tech.root: display
ms.assetid: 68C7EC44-D744-4C69-86D9-35B3B089875A
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DEALLOCATE2CB callback function"]
ms.keywords: PFND3DDDI_DEALLOCATE2CB, PFND3DDDI_DEALLOCATE2CB callback, d3dumddi/pfnDeallocate2Cb, display.pfndeallocate2cb, pfnDeallocate2Cb, pfnDeallocate2Cb callback function [Display Devices]
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
 - "d3dumddi/pfnDeallocate2Cb"
 - "pfnDeallocate2Cb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnDeallocate2Cb
product:
 - Windows
---

# PFND3DDDI_DEALLOCATE2CB callback function

## -description

The <b>pfnDeallocate2Cb</b> user mode callback function releases allocations for a kernel-mode resource object if the resource object was created.

<b>pfnDeallocate2Cb</b> is a replacement for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a> that has an additional <b>Flags</b> member. When <b>Flags</b> are set to all zeroes, behavior is equivalent to <i>pfnDeallocateCb</i>.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_deallocate2">D3DDDICB_DEALLOCATE2</a> structure that describes the resource to release.

## -returns

|Return code|Description|
|--- |--- |
|S_OK|The memory was successfully released.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.

## -remarks

When an allocation destruction request is received, VidMm assumes, by default, that commands queued prior to the destruction request may access the allocation being destroyed and defers the destruction operation until the queued commands finish. If the user mode driver (UMD) knows that pending commands don’t access the allocation being destroyed, it can instruct VidMm not to wait until pending commands are finished by setting the <b>AssumeNotInUse</b> flag to <b>TRUE</b> when calling <b>pfnDeallocate2Cb</b>.

If an application or UMD would like to ensure allocation memory is reclaimed prior to the return from the <b>pfnDeallocate2Cb</b> call (for example, to minimize peak memory usage if the surface is being re-created), it should set the <b>SynchronousDestroy</b> flag.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_deallocate2">D3DDDICB_DEALLOCATE2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a>

