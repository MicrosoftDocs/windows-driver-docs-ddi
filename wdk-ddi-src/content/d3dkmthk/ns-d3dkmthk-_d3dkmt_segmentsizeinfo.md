---
UID: NS:d3dkmthk._D3DKMT_SEGMENTSIZEINFO
title: "_D3DKMT_SEGMENTSIZEINFO"
author: windows-driver-content
description: The D3DKMT_SEGMENTSIZEINFO structure describes the size, in bytes, of memory and aperture segments.
old-location: display\d3dkmt_segmentsizeinfo.htm
old-project: display
ms.assetid: 16c7b4bd-efc9-4cce-8677-8046038d1c76
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SEGMENTSIZEINFO, D3DKMT_SEGMENTSIZEINFO structure [Display Devices], OpenGL_Structs_bdb19184-37f0-4341-b8bb-41011f6cb6b3.xml, _D3DKMT_SEGMENTSIZEINFO, d3dkmthk/D3DKMT_SEGMENTSIZEINFO, display.d3dkmt_segmentsizeinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_SEGMENTSIZEINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_SEGMENTSIZEINFO
---

# _D3DKMT_SEGMENTSIZEINFO structure


## -description


The D3DKMT_SEGMENTSIZEINFO structure describes the size, in bytes, of memory and aperture segments.


## -syntax


````
typedef struct _D3DKMT_SEGMENTSIZEINFO {
  ULONGLONG DedicatedVideoMemorySize;
  ULONGLONG DedicatedSystemMemorySize;
  ULONGLONG SharedSystemMemorySize;
} D3DKMT_SEGMENTSIZEINFO;
````


## -struct-fields




### -field DedicatedVideoMemorySize

[out] The size, in bytes, of memory that is dedicated from video memory.


### -field DedicatedSystemMemorySize

[out] The size, in bytes, of memory that is dedicated from system memory.


### -field SharedSystemMemorySize

[out] The size, in bytes, of memory from system memory that can be shared by many users.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>



 

 


