---
UID: NC:d3dumddi.PFND3DDDI_CREATECONTEXTVIRTUALCB
title: PFND3DDDI_CREATECONTEXTVIRTUALCB (d3dumddi.h)
description: pfnCreateContextVirtualCb should be used with contexts that support virtual addressing.
old-location: display\pfncreatecontextvirtualcb.htm
tech.root: display
ms.assetid: 7787FEDF-E18C-4120-A073-A13933856F57
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CREATECONTEXTVIRTUALCB, PFND3DDDI_CREATECONTEXTVIRTUALCB callback, d3dumddi/pfnCreateContextVirtualCb, display.pfncreatecontextvirtualcb, pfnCreateContextVirtualCb, pfnCreateContextVirtualCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3dumddi/pfnCreateContextVirtualCb"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnCreateContextVirtualCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATECONTEXTVIRTUALCB callback function


## -description


<b>pfnCreateContextVirtualCb</b> should be used with contexts that support virtual addressing.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *

pData [in, out]

A pointer to a [D3DDDICB_CREATECONTEXTVIRTUAL](../d3dumddi/ns-d3dumddi-_d3dddicb_createcontextvirtual.md) structure that describes the context to create.


## -returns

|Return code|Description|
|--- |--- |
|S_OK|The context was successfully created.|
|E_OUTOFMEMORY|Could not allocate memory that was required for the operation to complete.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

 

This function might also return other <b>HRESULT</b> values.



