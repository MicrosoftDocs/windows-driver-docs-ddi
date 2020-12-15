---
UID: NC:d3dkmthk.PFND3DKMT_CLOSEADAPTER
title: PFND3DKMT_CLOSEADAPTER (d3dkmthk.h)
description: The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function.
old-location: display\d3dkmtcloseadapter.htm
ms.date: 11/21/2018
keywords: ["PFND3DKMT_CLOSEADAPTER callback function"]
ms.keywords: D3DKMTCloseAdapter, D3DKMTCloseAdapter callback function [Display Devices], OpenGL_Functions_531edcbd-0ec0-4ae7-8a1a-31ed47084bba.xml, PFND3DKMT_CLOSEADAPTER, PFND3DKMT_CLOSEADAPTER callback, d3dkmthk/D3DKMTCloseAdapter, display.d3dkmtcloseadapter
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_CLOSEADAPTER
 - d3dkmthk/PFND3DKMT_CLOSEADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTCloseAdapter
product:
 - Windows
---

# PFND3DKMT_CLOSEADAPTER callback function


## -description

The <b>D3DKMTCloseAdapter</b> function closes an adapter that was previously opened by various functions.

## -parameters

### -param Arg1

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
- [D3DKMTCloseAdapter](nf-d3dkmthk-d3dkmtcloseadapter.md)
- [PFND3DKMT_ENUMADAPTERS2](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)

