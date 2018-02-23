---
UID: NS:d3dumddi._D3DDDIARG_SETDISPLAYMODE
title: "_D3DDDIARG_SETDISPLAYMODE"
author: windows-driver-content
description: The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode.
old-location: display\d3dddiarg_setdisplaymode.htm
old-project: display
ms.assetid: 4dd4c02f-af44-4b02-a646-b7648b430b89
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DDDIARG_SETDISPLAYMODE structure [Display Devices], display.d3dddiarg_setdisplaymode, d3dumddi/D3DDDIARG_SETDISPLAYMODE, _D3DDDIARG_SETDISPLAYMODE, D3DDDIARG_SETDISPLAYMODE, UMDisplayDriver_param_Structs_89fc526d-719f-43b5-b195-47a199a290ec.xml
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
-	D3DDDIARG_SETDISPLAYMODE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETDISPLAYMODE
---

# _D3DDDIARG_SETDISPLAYMODE structure


## -description


The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode. 


## -syntax


````
typedef struct _D3DDDIARG_SETDISPLAYMODE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} D3DDDIARG_SETDISPLAYMODE;
````


## -struct-fields




### -field hResource

[in] A handle to the resource that contains the display surface.


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the display surface.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymode.md">SetDisplayMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETDISPLAYMODE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

