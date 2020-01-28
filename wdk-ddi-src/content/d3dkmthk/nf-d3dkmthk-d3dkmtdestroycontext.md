---
UID: NF:d3dkmthk.D3DKMTDestroyContext
title: D3DKMTDestroyContext function (d3dkmthk.h)
description: The D3DKMTDestroyContext function releases a kernel-mode device context.
old-location: display\d3dkmtdestroycontext.htm
ms.assetid: 33c10139-7a9a-41b1-a3c4-e3692be9a34a
ms.date: 05/10/2018
ms.keywords: D3DKMTDestroyContext, D3DKMTDestroyContext function [Display Devices], OpenGL_Functions_f7a43a18-cb8c-4b76-8123-d5eeda18d6cb.xml, d3dkmthk/D3DKMTDestroyContext, display.d3dkmtdestroycontext
f1_keywords:
 - "d3dkmthk/D3DKMTDestroyContext"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTDestroyContext
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyContext function

## -description

The <b>D3DKMTDestroyContext</b> function releases a kernel-mode device context.

## -parameters

### -param D3DKMT_DESTROYCONTEXT

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroycontext">D3DKMT_DESTROYCONTEXT</a> structure that contains the handle to the kernel-mode device context.

## -returns

<b>D3DKMTDestroyContext</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully released.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroycontext">D3DKMT_DESTROYCONTEXT</a>
 

 

