---
UID: NS:d3dumddi._D3DDDIARG_LOCK
title: "_D3DDDIARG_LOCK"
author: windows-driver-content
description: The D3DDDIARG_LOCK structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lock.htm
old-project: display
ms.assetid: 00f8b16c-3ec1-48ac-930b-17aca16cc04f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDIARG_LOCK, D3DDDIARG_LOCK structure [Display Devices], G, I, K, L, O, R, UMDisplayDriver_param_Structs_484ea489-6a0a-466a-b4d2-39d6f0eb5642.xml, _, _D3DDDIARG_LOCK, d3dumddi/D3DDDIARG_LOCK, display.d3dddiarg_lock"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
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


#### - Range

[in] A D3DDDIRANGE structure that describes the subrange of the linear resource to lock.


#### - Area

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the subrectangle of the surface to lock.


#### - Box

[in] A D3DDDIBOX structure that describes the subvolume of the volume to lock.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_LOCK structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

