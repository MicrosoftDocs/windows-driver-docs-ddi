---
UID: NF:d3dkmthk.D3DKMTCloseAdapter
title: D3DKMTCloseAdapter function (d3dkmthk.h)
description: The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function.
old-location: display\d3dkmtcloseadapter.htm
ms.assetid: d8f1a47b-4ba0-41e0-a6e3-0589e1efcf06
ms.date: 11/21/2018
keywords: ["D3DKMTCloseAdapter function"]
ms.keywords: D3DKMTCloseAdapter, D3DKMTCloseAdapter callback function [Display Devices], OpenGL_Functions_531edcbd-0ec0-4ae7-8a1a-31ed47084bba.xml, PFND3DKMT_CLOSEADAPTER, PFND3DKMT_CLOSEADAPTER callback, d3dkmthk/D3DKMTCloseAdapter, display.d3dkmtcloseadapter
f1_keywords:
 - "d3dkmthk/D3DKMTCloseAdapter"
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
api_name:
- D3DKMTCloseAdapter
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCloseAdapter function

## -description


The <b>D3DKMTCloseAdapter</b> function closes an adapter that was previously opened by various functions.

## -parameters

### -param D3DKMT_CLOSEADAPTER

*\_In\_* *[D3DKMT_CLOSEADAPTER](ns-d3dkmthk-_d3dkmt_closeadapter.md)* * *pCloseAdapter*

Specifies the adapter to close.

## -returns

<b>D3DKMTCloseAdapter</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The adapter was closed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.|
 

This function might also return other NTSTATUS values.


## -see-also
- [D3DKMT_CLOSEADAPTER](ns-d3dkmthk-_d3dkmt_closeadapter.md)
- [PFND3DKMT_CLOSEADAPTER](nc-d3dkmthk-pfnd3dkmt_closeadapter.md)
- [D3DKMTEnumAdapters2](nf-d3dkmthk-d3dkmtenumadapters2.md)
