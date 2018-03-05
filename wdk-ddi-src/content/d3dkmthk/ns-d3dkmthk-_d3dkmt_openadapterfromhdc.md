---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMHDC
title: "_D3DKMT_OPENADAPTERFROMHDC"
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromhdc.htm
old-project: display
ms.assetid: db425b8c-4abd-4998-89bb-f6d9f066a3f6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_OPENADAPTERFROMHDC, D3DKMT_OPENADAPTERFROMHDC structure [Display Devices], OpenGL_Structs_a4c2aa1b-b17c-4e81-a0d2-9776cec61112.xml, _D3DKMT_OPENADAPTERFROMHDC, d3dkmthk/D3DKMT_OPENADAPTERFROMHDC, display.d3dkmt_openadapterfromhdc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENADAPTERFROMHDC
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMHDC
---

# _D3DKMT_OPENADAPTERFROMHDC structure


## -description


The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.


## -syntax


````
typedef struct _D3DKMT_OPENADAPTERFROMHDC {
  HDC                            hDc;
  D3DKMT_HANDLE                  hAdapter;
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_OPENADAPTERFROMHDC;
````


## -struct-fields




### -field hDc

[in] The HDC for the graphics adapter and monitor output that are retrieved.


### -field hAdapter

[out] A handle to the graphics adapter for the HDC that <b>hDc</b> specifies. The adapter handle is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromhdc.md">D3DKMTOpenAdapterFromHdc</a> function.


### -field AdapterLuid

[out] The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) of the graphics adapter for the HDC that <b>hDc</b> specifies. The LUID is returned from the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromhdc.md">D3DKMTOpenAdapterFromHdc</a> call.


### -field VidPnSourceId

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the HDC that <b>hDc</b> specifies. The identification number is returned from the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromhdc.md">D3DKMTOpenAdapterFromHdc</a> call.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromhdc.md">D3DKMTOpenAdapterFromHdc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENADAPTERFROMHDC structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

