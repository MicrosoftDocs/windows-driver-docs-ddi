---
UID: NS:d3dkmthk._D3DKMT_QUERYADAPTERINFO
title: _D3DKMT_QUERYADAPTERINFO (d3dkmthk.h)
description: The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dkmt_queryadapterinfo.htm
ms.assetid: 2bc9afc3-2fcf-4f62-85d4-67f824733904
ms.date: 11/21/2018
keywords: ["D3DKMT_QUERYADAPTERINFO structure"]
ms.keywords: D3DKMT_QUERYADAPTERINFO, D3DKMT_QUERYADAPTERINFO structure [Display Devices], OpenGL_Structs_10a338e9-c5a8-44e0-9ad7-87d5a3ab742e.xml, _D3DKMT_QUERYADAPTERINFO, d3dkmthk/D3DKMT_QUERYADAPTERINFO, display.d3dkmt_queryadapterinfo
f1_keywords:
 - "d3dkmthk/D3DKMT_QUERYADAPTERINFO"
 - "D3DKMT_QUERYADAPTERINFO"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Supported  starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_QUERYADAPTERINFO
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYADAPTERINFO
---

# _D3DKMT_QUERYADAPTERINFO structure

## -description
The D3DKMT_QUERYADAPTERINFO structure retrieves various information that describes the adapter.

## -struct-fields

### -field hAdapter
*D3DKMT\_HANDLE* *hAdapter*

A handle to the adapter that information is retrieved about.

### -field Type
*[KMTQUERYADAPTERINFOTYPE](ne-d3dkmthk-_kmtqueryadapterinfotype.md) Type*

Indicates the type of information to retrieve.

### -field pPrivateDriverData
*\_Inout\_bytecount\_(PrivateDriverDataSize)* *void * pPrivateDriverData*

A pointer to a memory region, which is interpreted based on the value of **Type**.

### -field PrivateDriverDataSize
*UINT PrivateDriverDataSize*

The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.

## -see-also
- [KMTQUERYADAPTERINFOTYPE](ne-d3dkmthk-_kmtqueryadapterinfotype.md)
- [D3DKMTQueryAdapterInfo](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
- [PFND3DKMT_QUERYADAPTERINFO](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)
 

