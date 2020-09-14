---
UID: NC:d3dumddi.PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB
title: PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB (d3dumddi.h)
description: pfnGetResourcePresentPrivateDriverDataCb is used to query the resource private data, which is associated with the resource during Present.
old-location: display\pfngetresourcepresentprivatedriverdatacb.htm
tech.root: display
ms.assetid: D4F0F272-60DC-4060-9762-3DB49236CE62
ms.date: 05/10/2018
keywords: ["PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB callback function"]
ms.keywords: PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB, PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB callback, d3dumddi/pfnGetResourcePresentPrivateDriverDataCb, display.pfngetresourcepresentprivatedriverdatacb, pfnGetResourcePresentPrivateDriverDataCb, pfnGetResourcePresentPrivateDriverDataCb callback function [Display Devices]
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
 - PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB
 - d3dumddi/PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnGetResourcePresentPrivateDriverDataCb
product:
 - Windows
---

# PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB callback function


## -description

<b>pfnGetResourcePresentPrivateDriverDataCb</b> is used to query the resource private data, which is associated with the resource during Present.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_getresourcepresentprivatedriverdata">D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA</a> structure that describes the operation to perform and contains the results.

## -returns

|Return value|Description|
|--- |--- |
|S_OK|The operation completed successfully.|
|STATUS_INVALID_BUFFER_SIZE|The value of D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA::PrivateDriverDataSize was zero or was insufficient to hold the data. When control returns to the caller, PrivateDriverDataSize will contain the required buffer size.|


This method may return other <b>HRESULT</b> values.

