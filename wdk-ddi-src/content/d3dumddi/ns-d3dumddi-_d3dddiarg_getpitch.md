---
UID: NS:d3dumddi._D3DDDIARG_GETPITCH
title: "_D3DDDIARG_GETPITCH"
author: windows-driver-content
description: The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the GetPitch function retrieves the pitch.
old-location: display\d3dddiarg_getpitch.htm
old-project: display
ms.assetid: 59661cfe-4a1f-4805-9421-7f694e82f8d2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DDDIARG_GETPITCH, UMDisplayDriver_param_Structs_02e95329-8eba-41a3-ae4e-d8830b47ada6.xml, D3DDDIARG_GETPITCH, d3dumddi/D3DDDIARG_GETPITCH, D3DDDIARG_GETPITCH structure [Display Devices], display.d3dddiarg_getpitch"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_GETPITCH is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_GETPITCH
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETPITCH
---

# _D3DDDIARG_GETPITCH structure


## -description


The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getpitch.md">GetPitch</a> function retrieves the pitch. 


## -syntax


````
typedef struct _D3DDDIARG_GETPITCH {
  HANDLE hCryptoSession;
  HANDLE hResource;
  UINT   SubResourceIndex;
  UINT   Pitch;
} D3DDDIARG_GETPITCH;
````


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session. 


### -field hResource

[in] A handle to the resource. 


### -field SubResourceIndex

[in] The zero-based index into the resource, which the <b>hResource</b> handle specifies. This index indicates the encrypted surface.


### -field Pitch

[out] The pitch, in bytes, of the encrypted surface. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getpitch.md">GetPitch</a> function returns this pitch value to the Direct3D runtime. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getpitch.md">GetPitch</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETPITCH structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

