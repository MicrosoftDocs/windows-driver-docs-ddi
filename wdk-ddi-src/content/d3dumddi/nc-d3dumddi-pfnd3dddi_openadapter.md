---
UID: NC:d3dumddi.PFND3DDDI_OPENADAPTER
title: PFND3DDDI_OPENADAPTER (d3dumddi.h)
description: The OpenAdapter function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\openadapter.htm
tech.root: display
ms.assetid: 41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16
ms.date: 05/10/2018
keywords: ["PFND3DDDI_OPENADAPTER callback function"]
ms.keywords: OpenAdapter, OpenAdapter callback function [Display Devices], PFND3DDDI_OPENADAPTER, PFND3DDDI_OPENADAPTER callback, UserModeDisplayDriver_Functions_1b93a0e5-3f89-47aa-9e63-3ae50f1acd1e.xml, d3dumddi/OpenAdapter, display.openadapter
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
 - "d3dumddi/OpenAdapter"
 - "OpenAdapter"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - OpenAdapter
product:
 - Windows
---

# PFND3DDDI_OPENADAPTER callback function

## -description

The <i>OpenAdapter</i> function creates a graphics adapter object that is referenced in subsequent calls.

## -parameters

### -param Arg1

*pOpenData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_openadapter">D3DDDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.

## -returns

<i>OpenAdapter</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The graphics adapter object is successfully created.|
|E_OUTOFMEMORY|OpenAdapter could not allocate the required memory for it to complete.|

## -remarks

The graphics adapter object that is created by <i>OpenAdapter</i> represents the underlying graphics hardware. Before the Microsoft Direct3D runtime can create a display device by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>, the user-mode display driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_openadapter">D3DDDIARG_OPENADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>

