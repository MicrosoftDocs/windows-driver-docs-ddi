---
UID: NS:d3dkmddi._DXGKARG_DESCRIBEALLOCATION
title: _DXGKARG_DESCRIBEALLOCATION
author: windows-driver-content
description: The DXGKARG_DESCRIBEALLOCATION structure describes an existing allocation.
old-location: display\dxgkarg_describeallocation.htm
old-project: display
ms.assetid: fd01ff3b-83b7-43d5-bbc6-6959485edd15
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_DESCRIBEALLOCATION, DXGKARG_DESCRIBEALLOCATION, *INOUT_PDXGKARG_DESCRIBEALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_DESCRIBEALLOCATION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGKARG_DESCRIBEALLOCATION
---

# _DXGKARG_DESCRIBEALLOCATION structure



## -description
The DXGKARG_DESCRIBEALLOCATION structure describes an existing allocation.



## -syntax

````
typedef struct _DXGKARG_DESCRIBEALLOCATION {
  HANDLE                       hAllocation;
  UINT                         Width;
  UINT                         Height;
  D3DDDIFORMAT                 Format;
  D3DDDI_MULTISAMPLINGMETHOD   MultisampleMethod;
  D3DDDI_RATIONAL              RefreshRate;
  UINT                         PrivateDriverFormatAttribute;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGK_DESCRIBEALLOCATIONFLAGS Flags;
  D3DDDI_ROTATION              Rotation;
#endif 
} DXGKARG_DESCRIBEALLOCATION;
````


## -struct-fields

### -field hAllocation

[in] A handle to an allocation that information is requested for. The driver previously returned this handle in the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure from a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function.


### -field Width

[out] The width of the allocation, in pixels. The driver returns the width value.


### -field Height

[out] The height of the allocation, in pixels. The driver returns the height value.


### -field Format

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation. The driver returns the format value.


### -field MultisampleMethod

[out] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_multisamplingmethod.md">D3DDDI_MULTISAMPLINGMETHOD</a> structure that describes the multiple-sampling method that is used for the allocation. The driver returns the description.


### -field RefreshRate

[out] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a> structure that indicates the refresh rate that the primary surface was created with, if applicable.


### -field PrivateDriverFormatAttribute

[out] A UINT value that specifies a private format attribute for the allocation. The driver specifies surface format attributes (for example, the pixel layout of a tiled surface) that it otherwise cannot expose to the operating system. 

The operating system uses the information in <b>PrivateDriverFormatAttribute</b> to compare two surfaces. For example, an A8R8B8G8 800x600 surface and an X8R8B8G8 800x600 surface should have the same information in <b>PrivateDriverFormatAttribute</b> if they have the same format attributes, which includes pixel layout. 


### -field Flags

[out] This member is reserved.

Supported starting with Windows 8.


### -field Rotation

[out] This member is reserved.

Supported starting with Windows 8.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_multisamplingmethod.md">D3DDDI_MULTISAMPLINGMETHOD</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_describeallocationflags.md">DXGK_DESCRIBEALLOCATIONFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_describeallocation.md">DxgkDdiDescribeAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_DESCRIBEALLOCATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

