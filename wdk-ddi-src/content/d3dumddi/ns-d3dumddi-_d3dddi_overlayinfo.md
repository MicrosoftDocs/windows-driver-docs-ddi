---
UID: NS:d3dumddi._D3DDDI_OVERLAYINFO
title: _D3DDDI_OVERLAYINFO (d3dumddi.h)
description: The D3DDDI_OVERLAYINFO structure describes information about an overlay.
old-location: display\d3dddi_overlayinfo.htm
tech.root: display
ms.assetid: e2732ea9-4fd6-416d-8fb0-1ccf1d1ad0df
ms.date: 05/10/2018
keywords: ["_D3DDDI_OVERLAYINFO structure"]
ms.keywords: D3DDDI_OVERLAYINFO, D3DDDI_OVERLAYINFO structure [Display Devices], D3D_other_Structs_b9046736-50b8-46b1-92c9-5d879ee7c64d.xml, _D3DDDI_OVERLAYINFO, d3dumddi/D3DDDI_OVERLAYINFO, display.d3dddi_overlayinfo
f1_keywords:
 - "d3dumddi/D3DDDI_OVERLAYINFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDI_OVERLAYINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYINFO
---

# _D3DDDI_OVERLAYINFO structure


## -description


The D3DDDI_OVERLAYINFO structure describes information about an overlay. 


## -struct-fields




### -field hResource

[in] A handle to the resource that is displayed by using the overlay. The resource is created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function with the <b>Overlay</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure that is pointed to by the <i>pResource</i> parameter.


### -field SubResourceIndex

[in] The index to the subresource if the resource that is specified by the <b>hResource</b> member contains a list of allocations. 


### -field DstRect

[in] A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure for the destination rectangle, which contains the output coordinates for the display. 


### -field SrcRect

[in] A RECT structure for the source rectangle that is displayed. 


### -field DstColorKeyLow

[in] A value for the destination color key when the <b>DstColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>DstColorKeyLow</b> contains the low end of the range. The value is in the native format of the primary surface that is overlayed. 


### -field DstColorKeyHigh

[in] The high end of the destination color key range when the <b>DstColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the primary surface that is overlayed. 


### -field SrcColorKeyLow

[in] A value for the source color key when the <b>SrcColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>SrcColorKeyLow</b> contains the low end of the range. The value is in the native format of the overlay resource that is displayed. 


### -field SrcColorKeyHigh

[in] The high end of the source color key range when the <b>SrcColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the overlay resource that is displayed. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfoflags">D3DDDI_OVERLAYINFOFLAGS</a> structure that identifies the type of overlay operation to perform. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.


## -remarks



The <b>SrcColorKey</b>, <b>SrcColorKeyRange</b>, <b>DstColorKey</b>, and <b>DstColorKeyRange</b> bit-field flags are never set simultaneously in the <b>Flags</b> member. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlay">CreateOverlay</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfoflags">D3DDDI_OVERLAYINFOFLAGS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updateoverlay">UpdateOverlay</a>
 

 

