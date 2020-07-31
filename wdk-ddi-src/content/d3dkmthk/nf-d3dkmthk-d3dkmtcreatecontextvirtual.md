---
UID: NF:d3dkmthk.D3DKMTCreateContextVirtual
title: D3DKMTCreateContextVirtual function (d3dkmthk.h)
description: The D3DKMTCreateContextVirtual function creates a kernel mode device context that supports virtual addressing.
old-location: display\d3dkmtcreatecontextvirtual.htm
ms.assetid: 1E95228E-7513-46D2-8402-28CA6D26F3EB
ms.date: 05/10/2018
keywords: ["D3DKMTCreateContextVirtual function"]
ms.keywords: D3DKMTCreateContextVirtual, D3DKMTCreateContextVirtual function [Display Devices], d3dkmthk/D3DKMTCreateContextVirtual, display.d3dkmtcreatecontextvirtual
f1_keywords:
 - "d3dkmthk/D3DKMTCreateContextVirtual"
 - "D3DKMTCreateContextVirtual"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTCreateContextVirtual
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateContextVirtual function

## -description

The <b>D3DKMTCreateContextVirtual</b> function creates a kernel mode device context that supports virtual addressing.

## -parameters

### -param Arg1

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createcontextvirtual">D3DKMT_CREATECONTEXTVIRTUAL</a> structure that describes the kernel-mode device context.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_NO_MEMORY|D3DKMTCreateContextVirtual could not complete because of insufficient memory.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createcontextvirtual">D3DKMT_CREATECONTEXTVIRTUAL</a>
 

 

