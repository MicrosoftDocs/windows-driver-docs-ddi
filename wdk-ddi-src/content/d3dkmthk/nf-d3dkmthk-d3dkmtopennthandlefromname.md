---
UID: NF:d3dkmthk.D3DKMTOpenNtHandleFromName
title: D3DKMTOpenNtHandleFromName function (d3dkmthk.h)
description: The D3DKMTOpenNtHandleFromName function opens an NT handle for a graphics adapter that is specified by name.
old-location: display\d3dkmtopennthandlefromname.htm
ms.date: 05/10/2018
keywords: ["D3DKMTOpenNtHandleFromName function"]
ms.keywords: D3DKMTOpenNtHandleFromName, D3DKMTOpenNtHandleFromName callback function [Display Devices], PFND3DKMT_OPENNTHANDLEFROMNAME, PFND3DKMT_OPENNTHANDLEFROMNAME callback, d3dkmthk/D3DKMTOpenNtHandleFromName, display.d3dkmtopennthandlefromname
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTOpenNtHandleFromName
 - d3dkmthk/D3DKMTOpenNtHandleFromName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTOpenNtHandleFromName
---

# D3DKMTOpenNtHandleFromName function


## -description

From a given graphics adapter name, opens an NT handle to the process.

## -parameters

### -param unnamedParam1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_opennthandlefromname">D3DKMT_OPENNTHANDLEFROMNAME</a> structure that describes information required to open an NT handle.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function completed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.
