---
UID: NS:d3dkmthk._D3DKMT_WORKINGSETFLAGS
title: "_D3DKMT_WORKINGSETFLAGS"
author: windows-driver-content
description: The D3DKMT_WORKINGSETFLAGS structure identifies working-set properties of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_workingsetflags.htm
old-project: display
ms.assetid: 05dddebc-2a30-4cc5-b905-9ee4ebf8d00e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_WORKINGSETFLAGS, D3DKMT_WORKINGSETFLAGS structure [Display Devices], OpenGL_Structs_4ce8b8d1-7f35-45b4-8b01-154a9a8eda00.xml, _D3DKMT_WORKINGSETFLAGS, d3dkmthk/D3DKMT_WORKINGSETFLAGS, display.d3dkmt_workingsetflags
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
-	D3DKMT_WORKINGSETFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_WORKINGSETFLAGS
---

# _D3DKMT_WORKINGSETFLAGS structure


## -description


The D3DKMT_WORKINGSETFLAGS structure identifies working-set properties of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _D3DKMT_WORKINGSETFLAGS {
  UINT UseDefault  :1;
  UINT Reserved  :31;
} D3DKMT_WORKINGSETFLAGS;
````


## -struct-fields




### -field UseDefault

A UINT value that specifies whether the display miniport driver uses the default working set.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros. 


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetinfo.md">D3DKMT_WORKINGSETINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>



 

 


