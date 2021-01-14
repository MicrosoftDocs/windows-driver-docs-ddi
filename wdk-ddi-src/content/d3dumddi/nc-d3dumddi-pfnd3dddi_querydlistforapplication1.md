---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION1
title: PFND3DDDI_QUERYDLISTFORAPPLICATION1 (d3dumddi.h)
description: Called during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A dList is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.
old-location: display\querydlistforapplication1.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function"]
ms.keywords: PFND3DDDI_QUERYDLISTFORAPPLICATION1, PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback, QueryDListForApplication, QueryDListForApplication callback function [Display Devices], d3dumddi/QueryDListForApplication, display.querydlistforapplication1
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
 - PFND3DDDI_QUERYDLISTFORAPPLICATION1
 - d3dumddi/PFND3DDDI_QUERYDLISTFORAPPLICATION1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - PFND3DDDI_QUERYDLISTFORAPPLICATION1
product:
 - Windows
---

# PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function


## -description

Called during Microsoft Direct3D initialization on a <a href="/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system">hybrid system</a> to determine which GPU an application should run on. A <i>dList</i> is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.

## -parameters

### -param Arg1

*pDefaultToDiscrete* [out]

If <b>TRUE</b>, the application should be run on the discrete GPU. Otherwise, the application should run on the integrated GPU.

### -param Arg2

*pfnEscapeCB* [in]

A function pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb">pfnEscapeCb</a> callback function that shares info with the display miniport driver.

### -param Arg3

## -returns

Returns <b>S_OK</b>, or an appropriate error result if the operation is not successful.

## -remarks

For more information on how to call this function and set up the DLL that exports it, see <a href="/windows-hardware/drivers/display/hybrid-system-ddi">Hybrid system DDI</a>.

For more general information on hybrid systems, see <a href="/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system">Using cross-adapter resources in a hybrid system</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb">pfnEscapeCb</a>

