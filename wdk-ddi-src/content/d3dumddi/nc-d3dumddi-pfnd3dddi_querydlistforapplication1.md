---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION1
title: PFND3DDDI_QUERYDLISTFORAPPLICATION1 (d3dumddi.h)
description: Called during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A dList is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.
old-location: display\querydlistforapplication1.htm
tech.root: display
ms.date: 11/02/2021
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
---

# PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function

## -description

The **PFND3DDDI_QUERYDLISTFORAPPLICATION1** function queries a dList for an application.

## -parameters

### -param unnamedParam1 [out]

If **TRUE**, the application should be run on the discrete GPU. Otherwise, the application should run on the integrated GPU.

### -param unnamedParam2 [in]

A handle to the graphics adapter object. This handle is passed to the [**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md) callback function pointed to by *unnamedParam3*.

### -param unnamedParam3 [in]

Pointer to a [**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md) callback function that shares info with the display miniport driver.

## -returns

Returns **S_OK**, or an appropriate error result if the operation is not successful.

## -remarks

Starting with WDDM 2.9, drivers must support [**PFND3DDDI_QUERYDLISTFORAPPLICATION2**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md) instead of **PFND3DDDI_QUERYDLISTFORAPPLICATION1**.

In WDDM versions prior to WDDM 2.9, **PFND3DDDI_QUERYDLISTFORAPPLICATION1** is called by the user-mode graphics runtime (DXGI) during Microsoft Direct3D initialization on a [hybrid system](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system) to determine which GPU an application should run on. A *dList* is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.

For more information on how to call this function and set up the DLL that exports it, see [Hybrid system DDI](/windows-hardware/drivers/display/hybrid-system-ddi).

For more general information on hybrid systems, see [Using cross-adapter resources in a hybrid system](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

## -see-also

[**PFND3DDDI_QUERYDLISTFORAPPLICATION2**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md)

[**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md)
