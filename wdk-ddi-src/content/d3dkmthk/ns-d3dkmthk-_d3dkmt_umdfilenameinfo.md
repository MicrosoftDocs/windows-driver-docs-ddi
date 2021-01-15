---
UID: NS:d3dkmthk._D3DKMT_UMDFILENAMEINFO
title: _D3DKMT_UMDFILENAMEINFO (d3dkmthk.h)
description: The D3DKMT_UMDFILENAMEINFO structure contains the name of an OpenGL ICD that is based on the specified version of the DirectX runtime.
old-location: display\d3dkmt_umdfilenameinfo.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_UMDFILENAMEINFO structure"]
ms.keywords: D3DKMT_UMDFILENAMEINFO, D3DKMT_UMDFILENAMEINFO structure [Display Devices], OpenGL_Structs_631f8c52-0978-4f26-bd6b-08348676795b.xml, _D3DKMT_UMDFILENAMEINFO, d3dkmthk/D3DKMT_UMDFILENAMEINFO, display.d3dkmt_umdfilenameinfo
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.typenames: D3DKMT_UMDFILENAMEINFO
f1_keywords:
 - _D3DKMT_UMDFILENAMEINFO
 - d3dkmthk/_D3DKMT_UMDFILENAMEINFO
 - D3DKMT_UMDFILENAMEINFO
 - d3dkmthk/D3DKMT_UMDFILENAMEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_UMDFILENAMEINFO
 - D3DKMT_UMDFILENAMEINFO
---

# _D3DKMT_UMDFILENAMEINFO structure


## -description

The D3DKMT_UMDFILENAMEINFO structure contains the name of an OpenGL ICD that is based on the specified version of the DirectX runtime.

## -struct-fields

### -field Version

[in] A KMTUMDVERSION-typed value that indicates the version of the DirectX runtime to retrieve the name of an OpenGL ICD for. The following table lists the possible values.

|Value|Meaning|
|--- |--- |
|KMTUMDVERSION_DX9 (0)|DirectX version 9.0|
|KMTUMDVERSION_DX10 (1)|DirectX version 10.0|
|KMTUMDVERSION_DX11 (2)|DirectX version 11.0|

### -field UmdFileName

[out] A string that contains the name of the OpenGL ICD.

