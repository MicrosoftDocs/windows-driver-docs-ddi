---
UID: NS:d3dumddi._DDICHECKOVERLAYSUPPORTINPUT
title: "_DDICHECKOVERLAYSUPPORTINPUT"
author: windows-driver-content
description: The DDICHECKOVERLAYSUPPORTINPUT structure describes an overlay display mode that the user-mode display driver uses to verify overlay support.
old-location: display\ddicheckoverlaysupportinput.htm
old-project: display
ms.assetid: 5f15743a-1ea7-4260-b2cb-f2871acb27f9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D_other_Structs_194edebf-9bbd-465b-a731-ad3e10f6e809.xml, DDICHECKOVERLAYSUPPORTINPUT, DDICHECKOVERLAYSUPPORTINPUT structure [Display Devices], _DDICHECKOVERLAYSUPPORTINPUT, d3dumddi/DDICHECKOVERLAYSUPPORTINPUT, display.ddicheckoverlaysupportinput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDICHECKOVERLAYSUPPORTINPUT is supported beginning with the Windows 7 operating system.
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
-	DDICHECKOVERLAYSUPPORTINPUT
product: Windows
targetos: Windows
req.typenames: DDICHECKOVERLAYSUPPORTINPUT
---

# _DDICHECKOVERLAYSUPPORTINPUT structure


## -description


The DDICHECKOVERLAYSUPPORTINPUT structure describes an overlay display mode that the user-mode display driver uses to verify overlay support. 


## -syntax


````
typedef struct _DDICHECKOVERLAYSUPPORTINPUT {
  UINT                    OverlayWidth;
  UINT                    OverlayHeight;
  D3DDDIFORMAT            OverlayFormat;
  UINT                    DisplayWidth;
  UINT                    DisplayHeight;
  UINT                    DisplayRefreshRate;
  D3DDDIFORMAT            DisplayFormat;
  D3DDDI_SCANLINEORDERING DisplayScanLineOrdering;
  D3DDDI_ROTATION         DisplayRotation;
} DDICHECKOVERLAYSUPPORTINPUT;
````


## -struct-fields




### -field OverlayWidth

[in] The width of the overlay in pixels. 


### -field OverlayHeight

[in] The height of the overlay in pixels. 


### -field OverlayFormat


      [in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the overlay. 
     


### -field DisplayWidth

[in] The screen width of the display in pixels. 


### -field DisplayHeight

[in] The screen height of the display in pixels. 


### -field DisplayRefreshRate

[in] The refresh rate of the display. 


### -field DisplayFormat

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the display. 


### -field DisplayScanLineOrdering

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_scanlineordering.md">D3DDDI_SCANLINEORDERING</a>-typed value that indicates how the scan lines are drawn on the display. 


### -field DisplayRotation

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>-typed value that indicates how the display is oriented. 


## -remarks



The runtime specifies a pointer to a DDICHECKOVERLAYSUPPORTINPUT structure in the <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure. The runtime also specifies the D3DDDICAPS_CHECKOVERLAYSUPPORT value in the <b>Type</b> member of D3DDDIARG_GETCAPS. The runtime specifies these values in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to determine if the driver supports the overlay that DDICHECKOVERLAYSUPPORTINPUT describes. The driver's <i>GetCaps</i> returns a pointer to a D3DOVERLAYCAPS structure that contains information about the capabilities of the overlay through the <b>pData</b> member of D3DDDIARG_GETCAPS if the driver supports the overlay.




## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_scanlineordering.md">D3DDDI_SCANLINEORDERING</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDICHECKOVERLAYSUPPORTINPUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

