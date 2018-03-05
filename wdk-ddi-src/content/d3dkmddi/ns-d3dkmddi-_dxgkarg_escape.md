---
UID: NS:d3dkmddi._DXGKARG_ESCAPE
title: "_DXGKARG_ESCAPE"
author: windows-driver-content
description: The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.
old-location: display\dxgkarg_escape.htm
old-project: display
ms.assetid: 73a1afa6-e156-4733-b204-a9cae4e18563
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_ESCAPE, DXGKARG_ESCAPE structure [Display Devices], DmStructs_1edfa7aa-7ba1-4abc-a453-253de2a191af.xml, _DXGKARG_ESCAPE, d3dkmddi/DXGKARG_ESCAPE, display.dxgkarg_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_ESCAPE
product: Windows
targetos: Windows
req.typenames: DXGKARG_ESCAPE
---

# _DXGKARG_ESCAPE structure


## -description


The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.


## -syntax


````
typedef struct _DXGKARG_ESCAPE {
  HANDLE             hDevice;
  D3DDDI_ESCAPEFLAGS Flags;
  VOID               *pPrivateDriverData;
  UINT               PrivateDriverDataSize;
  HANDLE             hContext;
} DXGKARG_ESCAPE;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) that was originally passed to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information.


### -field pPrivateDriverData

[in/out] A pointer to a buffer that contains the information that the display miniport driver and the user-mode display driver share.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


### -field hContext

[in] A handle to the context that was originally passed to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_ESCAPE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

