---
UID: NS:d3dumddi._D3DDDIARG_LOCKASYNC
title: _D3DDDIARG_LOCKASYNC (d3dumddi.h)
description: The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lockasync.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_LOCKASYNC structure"]
ms.keywords: D3DDDIARG_LOCKASYNC, D3DDDIARG_LOCKASYNC structure [Display Devices], UMDisplayDriver_param_Structs_24593944-e4ac-4650-82d5-c5fc26a6a770.xml, _D3DDDIARG_LOCKASYNC, d3dumddi/D3DDDIARG_LOCKASYNC, display.d3dddiarg_lockasync
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
req.typenames: D3DDDIARG_LOCKASYNC
f1_keywords:
 - _D3DDDIARG_LOCKASYNC
 - d3dumddi/_D3DDDIARG_LOCKASYNC
 - D3DDDIARG_LOCKASYNC
 - d3dumddi/D3DDDIARG_LOCKASYNC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_LOCKASYNC
---

# _D3DDDIARG_LOCKASYNC structure


## -description

The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock.

## -struct-fields

### -field hResource

[in] A handle to the resource to be locked.

### -field SubResourceIndex

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be locked.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_lockasyncflags">D3DDDI_LOCKASYNCFLAGS</a> structure that indicates, in bit-field flags, how to lock the resource. 

<div class="alert"><b>Note</b>    Some flags are mutually exclusive with other flags. For more information, see the following Remarks section.</div>
<div> </div>

### -field Range

[in] A D3DDDIRANGE structure that describes the subrange of the linear resource to lock, if the <b>RangeValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.

### -field Area

[in] A <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that describes the subrectangle of the surface to lock, if the <b>AreaValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.

### -field Box

[in] A D3DDDIBOX structure that describes the subvolume of the volume to lock, if the <b>BoxValid</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.

### -field hCookie

[out] A handle that represents the renamed resource. This handle is valid only if the <b>Discard</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.

### -field pSurfData

[out] A pointer to the memory region for the resource that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function returns this pointer to the Microsoft Direct3D runtime.

### -field Pitch

[out] The pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function returns this pitch value to the Direct3D runtime.

### -field SlicePitch

[out] The slice pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function returns this slice pitch value to the Direct3D runtime.

### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.

## -remarks

The members of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_lockasyncflags">D3DDDI_LOCKASYNCFLAGS</a> structure that the <b>Flags</b> member specifies must adhere to the following rules:

<ul>
<li>
The <b>NoOverwrite</b> bit-field flag must not be simultaneously set with the <b>Discard</b> bit-field flag.

</li>
<li>
Only one of the <b>RangeValid</b>, <b>AreaValid</b>, and <b>BoxValid</b> bit-field flags must be set at any time.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_lockasyncflags">D3DDDI_LOCKASYNCFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>



<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>
