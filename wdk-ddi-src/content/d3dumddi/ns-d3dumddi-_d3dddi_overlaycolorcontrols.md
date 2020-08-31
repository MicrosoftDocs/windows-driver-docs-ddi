---
UID: NS:d3dumddi._D3DDDI_OVERLAYCOLORCONTROLS
title: _D3DDDI_OVERLAYCOLORCONTROLS (d3dumddi.h)
description: The D3DDDI_OVERLAYCOLORCONTROLS structure describes color-control settings for an overlay.
old-location: display\d3dddi_overlaycolorcontrols.htm
tech.root: display
ms.assetid: 201fd9e8-74c3-4da0-b01d-f43f9aec4894
ms.date: 05/10/2018
keywords: ["D3DDDI_OVERLAYCOLORCONTROLS structure"]
ms.keywords: D3DDDI_OVERLAYCOLORCONTROLS, D3DDDI_OVERLAYCOLORCONTROLS structure [Display Devices], D3D_other_Structs_276dd56c-35ba-4ee4-97d7-adb8dfd59c7f.xml, _D3DDDI_OVERLAYCOLORCONTROLS, d3dumddi/D3DDDI_OVERLAYCOLORCONTROLS, display.d3dddi_overlaycolorcontrols
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
req.typenames: D3DDDI_OVERLAYCOLORCONTROLS
f1_keywords:
 - _D3DDDI_OVERLAYCOLORCONTROLS
 - d3dumddi/_D3DDDI_OVERLAYCOLORCONTROLS
 - D3DDDI_OVERLAYCOLORCONTROLS
 - d3dumddi/D3DDDI_OVERLAYCOLORCONTROLS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDI_OVERLAYCOLORCONTROLS
---

# _D3DDDI_OVERLAYCOLORCONTROLS structure


## -description

The D3DDDI_OVERLAYCOLORCONTROLS structure describes color-control settings for an overlay.

## -struct-fields

### -field BrightnessSetting

[in] An INT value that specifies the brightness of the output image as it is written to the overlay. This member is set if the <b>Brightness</b> bit-field flag is set in the <b>Flags</b> member.

### -field ContrastSetting

[in] An INT value that specifies the contrast of the output image as it is written to the overlay. This member is set if the <b>Contrast</b> bit-field flag is set in the <b>Flags</b> member.

### -field HueSetting

[in] An INT value that specifies the hue of the output image as it is written to the overlay. This member is set if the <b>Hue</b> bit-field flag is set in the <b>Flags</b> member.

### -field SaturationSetting

[in] An INT value that specifies the saturation of the output image as it is written to the overlay. This member is set if the <b>Saturation</b> bit-field flag is set in the <b>Flags</b> member.

### -field SharpnessSetting

[in] An INT value that specifies the sharpness of the output image as it is written to the overlay. This member is set if the <b>Sharpness</b> bit-field flag is set in the <b>Flags</b> member.

### -field GammaSetting

[in] An INT value that specifies the gamma setting of the output image as it is written to the overlay. This member is set if the <b>Gamma</b> bit-field flag is set in the <b>Flags</b> member.

### -field ColorEnableSetting

[in] An INT value that specifies the color-enable setting of the output image as it is written to the overlay. This member is set if the <b>ColorEnable</b> bit-field flag is set in the <b>Flags</b> member.

### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlaycolorcontrolsflags">D3DDDI_OVERLAYCOLORCONTROLSFLAGS</a> structure that identifies color-control settings that the overlay hardware supports.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setoverlaycolorcontrols">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlaycolorcontrolsflags">D3DDDI_OVERLAYCOLORCONTROLSFLAGS</a>

