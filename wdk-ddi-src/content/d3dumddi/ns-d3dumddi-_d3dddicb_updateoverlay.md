---
UID: NS:d3dumddi._D3DDDICB_UPDATEOVERLAY
title: "_D3DDDICB_UPDATEOVERLAY"
author: windows-driver-content
description: The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dddicb_updateoverlay.htm
old-project: display
ms.assetid: efa54d23-99bc-49ea-b8a3-7ea5b00e36d8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D_param_Structs_b9e39db9-44ba-45d5-9500-dd9d5d8cc4bb.xml, d3dumddi/D3DDDICB_UPDATEOVERLAY, display.d3dddicb_updateoverlay, D3DDDICB_UPDATEOVERLAY structure [Display Devices], D3DDDICB_UPDATEOVERLAY, _D3DDDICB_UPDATEOVERLAY
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
-	D3DDDICB_UPDATEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_UPDATEOVERLAY
---

# _D3DDDICB_UPDATEOVERLAY structure


## -description


The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.


## -syntax


````
typedef struct _D3DDDICB_UPDATEOVERLAY {
  D3DKMT_HANDLE            hKernelOverlay;
  D3DDDI_KERNELOVERLAYINFO OverlayInfo;
} D3DDDICB_UPDATEOVERLAY;
````


## -struct-fields




### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to modify. 


### -field OverlayInfo

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_UPDATEOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

