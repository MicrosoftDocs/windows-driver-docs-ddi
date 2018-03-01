---
UID: NS:d3dumddi._D3DDDICB_FLIPOVERLAY
title: "_D3DDDICB_FLIPOVERLAY"
author: windows-driver-content
description: The D3DDDICB_FLIPOVERLAY structure describes a new allocation to display for the overlay.
old-location: display\d3dddicb_flipoverlay.htm
old-project: display
ms.assetid: 709583a5-5367-4187-a560-29b2c8eedbf4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_FLIPOVERLAY, D3DDDICB_FLIPOVERLAY structure [Display Devices], D3D_param_Structs_cb3914df-9c6b-43f0-a8fa-a2f06f5b2abd.xml, _D3DDDICB_FLIPOVERLAY, d3dumddi/D3DDDICB_FLIPOVERLAY, display.d3dddicb_flipoverlay
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
-	D3DDDICB_FLIPOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_FLIPOVERLAY
---

# _D3DDDICB_FLIPOVERLAY structure


## -description


The D3DDDICB_FLIPOVERLAY structure describes a new allocation to display for the overlay. 


## -syntax


````
typedef struct _D3DDDICB_FLIPOVERLAY {
  D3DKMT_HANDLE hKernelOverlay;
  D3DKMT_HANDLE hSource;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DDDICB_FLIPOVERLAY;
````


## -struct-fields




### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to be flipped.


### -field hSource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation to be displayed.


### -field pPrivateDriverData

[in] A pointer to a block of private data, which is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that is pointed to by <b>pPrivateDriverData</b>.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_FLIPOVERLAY structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

