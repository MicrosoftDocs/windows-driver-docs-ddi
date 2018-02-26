---
UID: NE:d3dumddi.D3DDDI_MARKERTYPE
title: D3DDDI_MARKERTYPE
author: windows-driver-content
description: Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.
old-location: display\d3dddi_markertype.htm
old-project: display
ms.assetid: 55A48F87-B96C-42E7-B9B4-3C829097CAE9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, D, D3DDDIMT_NONE, D3DDDIMT_PROFILE, D3DDDI_MARKERTYPE, D3DDDI_MARKERTYPE enumeration [Display Devices], E, I, K, M, P, R, T, Y, _, d3dumddi/D3DDDIMT_NONE, d3dumddi/D3DDDIMT_PROFILE, d3dumddi/D3DDDI_MARKERTYPE, display.d3dddi_markertype"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
apiname:
-	D3DDDI_MARKERTYPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_MARKERTYPE
---

# D3DDDI_MARKERTYPE enumeration


## -description


Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.


## -syntax


````
typedef enum D3DDDI_MARKERTYPE { 
  D3DDDIMT_NONE,
  D3DDDIMT_PROFILE
} D3DDDI_MARKERTYPE;
````


## -enum-fields




### -field D3DDDIMT_NONE

No marker type is supported. This type is set on creation of the display device.


### -field D3DDDIMT_PROFILE

Profile mode, where the driver estimates the length of time the GPU takes to execute certain operations. The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.

See Remarks of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarkermode.md">pfnSetMarkerMode</a> function for more info.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarkermode.md">pfnSetMarkerMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MARKERTYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

