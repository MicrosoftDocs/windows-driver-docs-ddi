---
UID: NC:d3dumddi.PFND3DDDI_EVICTCB
title: PFND3DDDI_EVICTCB (d3dumddi.h)
description: pfnEvictCb is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
old-location: display\pfnevictcb.htm
tech.root: display
ms.assetid: 5E66A522-BC1C-4E7C-8732-87D40F99BBDA
ms.date: 05/10/2018
keywords: ["PFND3DDDI_EVICTCB callback function"]
ms.keywords: PFND3DDDI_EVICTCB, PFND3DDDI_EVICTCB callback, d3dumddi/pfnEvictCb, display.pfnevictcb, pfnEvictCb, pfnEvictCb callback function [Display Devices]
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
 - "d3dumddi/pfnEvictCb"
 - "pfnEvictCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnEvictCb
product:
 - Windows
---

# PFND3DDDI_EVICTCB callback function

## -description

<b>pfnEvictCb</b> is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_evict">D3DDDICB_EVICT</a> structure that describes the memory pages to evict.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an HRESULT error code.

## -remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_evict">D3DDDICB_EVICT</a>

