---
UID: NS:d3dumddi._DXVADDI_QUERYPROCAMPINPUT
title: "_DXVADDI_QUERYPROCAMPINPUT"
author: windows-driver-content
description: The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.
old-location: display\dxvaddi_queryprocampinput.htm
old-project: display
ms.assetid: 9ba7c42a-4140-4d8c-abb3-ae5f9285dbd9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXVADDI_QUERYPROCAMPINPUT, DXVA2_Structs_64cd50ed-940a-46a1-8a4d-b43d40e85b25.xml, DXVADDI_QUERYPROCAMPINPUT, display.dxvaddi_queryprocampinput, DXVADDI_QUERYPROCAMPINPUT structure [Display Devices], d3dumddi/DXVADDI_QUERYPROCAMPINPUT"
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
-	DXVADDI_QUERYPROCAMPINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_QUERYPROCAMPINPUT
---

# _DXVADDI_QUERYPROCAMPINPUT structure


## -description


The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.


## -syntax


````
typedef struct _DXVADDI_QUERYPROCAMPINPUT {
  const GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
  UINT              ProcAmpCap;
} DXVADDI_QUERYPROCAMPINPUT;
````


## -struct-fields




#### - pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


#### - VideoDesc

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a> structure that describes the video stream. 


#### - RenderTargetFormat

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


#### - ProcAmpCap

[in] A ProcAmp control property that range information is requested for. The ProcAmp control property can be one of the members of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_procampvalues.md">DXVADDI_PROCAMPVALUES</a> structure. 


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_procampvalues.md">DXVADDI_PROCAMPVALUES</a>

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_valuerange.md">DXVADDI_VALUERANGE</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_QUERYPROCAMPINPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

