---
UID: NS:d3dumddi._D3DDDICB_ESCAPE
title: "_D3DDDICB_ESCAPE"
author: windows-driver-content
description: The D3DDDICB_ESCAPE structure describes information that a user-mode display driver shares with a display miniport driver.
old-location: display\d3dddicb_escape.htm
old-project: display
ms.assetid: 37e111be-5175-40d0-b862-0cc79d77d2bc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_ESCAPE, display.d3dddicb_escape, D3D_param_Structs_3981c7f8-973d-42c4-abfa-29613731df50.xml, D3DDDICB_ESCAPE structure [Display Devices], d3dumddi/D3DDDICB_ESCAPE, _D3DDDICB_ESCAPE
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
-	D3DDDICB_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_ESCAPE
---

# _D3DDDICB_ESCAPE structure


## -description


The D3DDDICB_ESCAPE structure describes information that a user-mode display driver shares with a display miniport driver.


## -syntax


````
typedef struct _D3DDDICB_ESCAPE {
  HANDLE             hDevice;
  D3DDDI_ESCAPEFLAGS Flags;
  VOID               *pPrivateDriverData;
  UINT               PrivateDriverDataSize;
  HANDLE             hContext;
} D3DDDICB_ESCAPE;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) that was originally passed to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function or <b>NULL</b>, if the shared information is not associated with a display device.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information. The user-mode display driver should specify the <b>HardwareAccess</b> bit-field flag to indicate that the display miniport driver must access graphics hardware in such a way that the operating system must perform the <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level of synchronization</a> into the display miniport driver for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> call. 


### -field pPrivateDriverData

[in/out] A pointer to a buffer that is allocated by the user-mode display driver that contains information that the user-mode display driver sends to the display miniport driver or that the user-mode display driver receives from the display miniport driver.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


### -field hContext

[in] A handle to the context that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function returned or <b>NULL</b>, if the shared information is not associated with a context. If the user-mode display driver sets <b>hContext</b> to a non-<b>NULL</b> value, the driver must have also set <b>hDevice</b> to a non-<b>NULL</b> value, and <b>hDevice</b> must correspond to the device that owns the context.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_ESCAPE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

