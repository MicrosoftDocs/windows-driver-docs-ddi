---
UID: NS:d3dumddi._D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
title: "_D3DDDIARG_SETVIDEOPROCESSRENDERTARGET"
author: windows-driver-content
description: The D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure describes the render target surface for video processing.
old-location: display\d3dddiarg_setvideoprocessrendertarget.htm
old-project: display
ms.assetid: f92aebbf-f163-45fa-ad8e-c13a36f08458
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_SETVIDEOPROCESSRENDERTARGET, display.d3dddiarg_setvideoprocessrendertarget, D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure [Display Devices], _D3DDDIARG_SETVIDEOPROCESSRENDERTARGET, UMDisplayDriver_param_Structs_8a00fe2d-be28-4577-831f-45fbdcfbbb1d.xml, d3dumddi/D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
---

# _D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure


## -description


The D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure describes the render target surface for video processing. 


## -syntax


````
typedef struct _D3DDDIARG_SETVIDEOPROCESSRENDERTARGET {
  HANDLE hVideoProcess;
  HANDLE hRenderTarget;
  UINT   SubResourceIndex;
} D3DDDIARG_SETVIDEOPROCESSRENDERTARGET;
````


## -struct-fields




### -field hVideoProcess

[in] A handle to the Microsoft DirectX Video Acceleration (DirectX VA) video processing device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a> function.


### -field hRenderTarget

[in] A handle to the render target surface for video processing.


### -field SubResourceIndex

[in] An index into the resource for the render target surface.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvideoprocessrendertarget.md">SetVideoProcessRenderTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

