---
UID: NS:d3dumddi._D3DDDI_OVERLAYINFO
title: "_D3DDDI_OVERLAYINFO"
author: windows-driver-content
description: The D3DDDI_OVERLAYINFO structure describes information about an overlay.
old-location: display\d3dddi_overlayinfo.htm
old-project: display
ms.assetid: e2732ea9-4fd6-416d-8fb0-1ccf1d1ad0df
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_OVERLAYINFO, D3DDDI_OVERLAYINFO structure [Display Devices], D3D_other_Structs_b9046736-50b8-46b1-92c9-5d879ee7c64d.xml, _D3DDDI_OVERLAYINFO, d3dumddi/D3DDDI_OVERLAYINFO, display.d3dddi_overlayinfo
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
-	D3DDDI_OVERLAYINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYINFO
---

# _D3DDDI_OVERLAYINFO structure


## -description


The D3DDDI_OVERLAYINFO structure describes information about an overlay. 


## -struct-fields




### -field hResource

[in] A handle to the resource that is displayed by using the overlay. The resource is created through a call to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function with the <b>Overlay</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure that is pointed to by the <i>pResource</i> parameter.


### -field SubResourceIndex

[in] The index to the subresource if the resource that is specified by the <b>hResource</b> member contains a list of allocations. 


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the destination rectangle, which contains the output coordinates for the display. 


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

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544626">D3DDDI_OVERLAYINFOFLAGS</a> structure that identifies the type of overlay operation to perform. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.


## -remarks



The <b>SrcColorKey</b>, <b>SrcColorKeyRange</b>, <b>DstColorKey</b>, and <b>DstColorKeyRange</b> bit-field flags are never set simultaneously in the <b>Flags</b> member. 




## -see-also




<a href="https://msdn.microsoft.com/761377ff-95a6-426b-8372-3f347870f9c4">CreateOverlay</a>



<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544626">D3DDDI_OVERLAYINFOFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="https://msdn.microsoft.com/80d7cc5c-51d8-4b91-9581-b073f9b0e68a">UpdateOverlay</a>
 

 

