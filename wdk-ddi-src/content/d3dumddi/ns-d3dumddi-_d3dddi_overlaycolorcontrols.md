---
UID: NS:d3dumddi._D3DDDI_OVERLAYCOLORCONTROLS
title: "_D3DDDI_OVERLAYCOLORCONTROLS"
author: windows-driver-content
description: The D3DDDI_OVERLAYCOLORCONTROLS structure describes color-control settings for an overlay.
old-location: display\d3dddi_overlaycolorcontrols.htm
old-project: display
ms.assetid: 201fd9e8-74c3-4da0-b01d-f43f9aec4894
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_OVERLAYCOLORCONTROLS, D3DDDI_OVERLAYCOLORCONTROLS structure [Display Devices], display.d3dddi_overlaycolorcontrols, D3D_other_Structs_276dd56c-35ba-4ee4-97d7-adb8dfd59c7f.xml, d3dumddi/D3DDDI_OVERLAYCOLORCONTROLS, _D3DDDI_OVERLAYCOLORCONTROLS
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
-	D3DDDI_OVERLAYCOLORCONTROLS
product: Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYCOLORCONTROLS
---

# _D3DDDI_OVERLAYCOLORCONTROLS structure


## -description


The D3DDDI_OVERLAYCOLORCONTROLS structure describes color-control settings for an overlay. 


## -syntax


````
typedef struct _D3DDDI_OVERLAYCOLORCONTROLS {
  INT                              BrightnessSetting;
  INT                              ContrastSetting;
  INT                              HueSetting;
  INT                              SaturationSetting;
  INT                              SharpnessSetting;
  INT                              GammaSetting;
  INT                              ColorEnableSetting;
  D3DDDI_OVERLAYCOLORCONTROLSFLAGS Flags;
} D3DDDI_OVERLAYCOLORCONTROLS;
````


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

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrolsflags.md">D3DDDI_OVERLAYCOLORCONTROLSFLAGS</a> structure that identifies color-control settings that the overlay hardware supports.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setoverlaycolorcontrols.md">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols.md">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrolsflags.md">D3DDDI_OVERLAYCOLORCONTROLSFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OVERLAYCOLORCONTROLS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

