---
UID: NS:d3dumddi._D3DDDIARG_LOCK
title: _D3DDDIARG_LOCK (d3dumddi.h)
description: The D3DDDIARG_LOCK structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lock.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_LOCK structure"]
ms.keywords: D3DDDIARG_LOCK, D3DDDIARG_LOCK structure [Display Devices], UMDisplayDriver_param_Structs_484ea489-6a0a-466a-b4d2-39d6f0eb5642.xml, _D3DDDIARG_LOCK, d3dumddi/D3DDDIARG_LOCK, display.d3dddiarg_lock
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
targetos: Windows
req.typenames: D3DDDIARG_LOCK
f1_keywords:
 - _D3DDDIARG_LOCK
 - d3dumddi/_D3DDDIARG_LOCK
 - D3DDDIARG_LOCK
 - d3dumddi/D3DDDIARG_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_LOCK
 - D3DDDIARG_LOCK
---

# _D3DDDIARG_LOCK structure


## -description

The D3DDDIARG_LOCK structure describes a resource or a surface within the resource to lock.

## -struct-fields

### -field hResource [in]

A handle to the resource to be locked.

### -field SubResourceIndex [in]

The zero-based index into the resource, which is specified by the handle that is specified by <b>hResource</b>. This index indicates the subresource or surface to be locked.

### -field Range [in]

A D3DDDIRANGE structure that describes the subrange of the linear resource to lock.

### -field Area [in]

A <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that describes the subrectangle of the surface to lock.

### -field Box [in]

A D3DDDIBOX structure that describes the subvolume of the volume to lock.

### -field pSurfData [out]

A pointer to the memory region for the resource that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> function returns this pointer to the Microsoft Direct3D runtime.

### -field Pitch [out]

The pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> function returns this pitch value to the Direct3D runtime.

### -field SlicePitch [out]

The slice pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> function returns this slice pitch value to the Direct3D runtime.

### -field Flags [in]

A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_lockflags">D3DDDI_LOCKFLAGS</a> structure that indicates, in bit-field flags, how to lock the resource. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.

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

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_lockflags">D3DDDI_LOCKFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a>

