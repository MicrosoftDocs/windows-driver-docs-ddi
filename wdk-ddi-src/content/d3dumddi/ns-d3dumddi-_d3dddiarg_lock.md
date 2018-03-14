---
UID: NS:d3dumddi._D3DDDIARG_LOCK
title: "_D3DDDIARG_LOCK"
author: windows-driver-content
description: The D3DDDIARG_LOCK structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lock.htm
old-project: display
ms.assetid: 00f8b16c-3ec1-48ac-930b-17aca16cc04f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_LOCK, D3DDDIARG_LOCK structure [Display Devices], UMDisplayDriver_param_Structs_484ea489-6a0a-466a-b4d2-39d6f0eb5642.xml, _D3DDDIARG_LOCK, d3dumddi/D3DDDIARG_LOCK, display.d3dddiarg_lock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_LOCK
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_LOCK
---

# _D3DDDIARG_LOCK structure


## -description


The D3DDDIARG_LOCK structure describes a resource or a surface within the resource to lock. 


## -syntax


````
typedef struct _D3DDDIARG_LOCK {
  HANDLE           hResource;
  UINT             SubResourceIndex;
  union {
    D3DDDIRANGE Range;
    RECT        Area;
    D3DDDIBOX   Box;
  };
  VOID             *pSurfData;
  UINT             Pitch;
  UINT             SlicePitch;
  D3DDDI_LOCKFLAGS Flags;
} D3DDDIARG_LOCK;
````


## -struct-fields




### -field hResource

[in] A handle to the resource to be locked. 


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle that is specified by <b>hResource</b>. This index indicates the subresource or surface to be locked.


### -field pSurfData

[out] A pointer to the memory region for the resource that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function returns this pointer to the Microsoft Direct3D runtime.


### -field Pitch

[out] The pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function returns this pitch value to the Direct3D runtime.


### -field SlicePitch

[out] The slice pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function returns this slice pitch value to the Direct3D runtime.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockflags.md">D3DDDI_LOCKFLAGS</a> structure that indicates, in bit-field flags, how to lock the resource. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.


#### - Area

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the subrectangle of the surface to lock.


#### - Box

[in] A D3DDDIBOX structure that describes the subvolume of the volume to lock.


#### - Range

[in] A D3DDDIRANGE structure that describes the subrange of the linear resource to lock.


## -remarks



The members of the structure that is specified by the <b>Flags</b> member must adhere to the following rules:

<ul>
<li>
The <b>ReadOnly</b> and <b>WriteOnly</b> bit-field flags must not be set simultaneously.

</li>
<li>
The <b>NoOverwrite</b> bit-field flag must not be simultaneously set with the <b>Discard</b> bit-field flag.

</li>
<li>
Only one of the <b>RangeValid</b>, <b>AreaValid</b>, and <b>BoxValid</b> bit-field flags must be set at any time.

</li>
<li>
The <b>ReadOnly</b> bit-field flag must not be simultaneously set with the <b>Discard</b> bit-field flag.

</li>
</ul>



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockflags.md">D3DDDI_LOCKFLAGS</a>



 

 


