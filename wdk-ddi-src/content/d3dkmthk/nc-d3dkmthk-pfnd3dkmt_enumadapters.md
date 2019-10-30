---
UID: NC:d3dkmthk.PFND3DKMT_ENUMADAPTERS
title: PFND3DKMT_ENUMADAPTERS (d3dkmthk.h)
description: Enumerates all graphics adapters on the system.
old-location: display\d3dkmtenumadapters.htm
ms.assetid: 07c0aeac-0f82-492a-aa98-0ba5a962b9cf
ms.date: 05/10/2018
ms.keywords: D3DKMTEnumAdapters, D3DKMTEnumAdapters callback function [Display Devices], PFND3DKMT_ENUMADAPTERS, PFND3DKMT_ENUMADAPTERS callback, d3dkmthk/D3DKMTEnumAdapters, display.d3dkmtenumadapters
ms.topic: callback
f1_keywords:
 - "d3dkmthk/D3DKMTEnumAdapters"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmthk.h
api_name:
- D3DKMTEnumAdapters
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_ENUMADAPTERS callback function

## -description

Enumerates all graphics adapters on the system.

## -parameters

### -param *

*pEnumAdapters* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_enumadapters">D3DKMT_ENUMADAPTERS</a> structure that lists all graphics adapters and their characteristics.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The enumeration was successful.|
|STATUS_INVALID_PARAMETER|The  pEnumAdapters parameter was validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -remarks

The operating system enumerates graphics adapters in the same sequence as their corresponding physical devices.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_enumadapters">D3DKMT_ENUMADAPTERS</a>
 
