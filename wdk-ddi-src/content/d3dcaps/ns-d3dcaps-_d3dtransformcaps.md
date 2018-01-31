---
UID: NS:d3dcaps._D3DTRANSFORMCAPS
title: "_D3DTRANSFORMCAPS"
author: windows-driver-content
description: Obsolete in DirectX 8.0 and later versions. D3DTRANSFORMCAPS structure describes the transform capabilities of a device.
old-location: display\d3dtransformcaps.htm
old-project: display
ms.assetid: 4eb6c31d-97b2-4d51-ae49-ed2ab395188a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dcaps/LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS, d3dcaps/D3DTRANSFORMCAPS, display.d3dtransformcaps, LPD3DTRANSFORMCAPS, _D3DTRANSFORMCAPS, D3DTRANSFORMCAPS structure [Display Devices], LPD3DTRANSFORMCAPS structure pointer [Display Devices], *LPD3DTRANSFORMCAPS, d3dstrct_9dc73cc8-edfd-424e-b902-0305de356c07.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dcaps.h
req.include-header: D3dcaps.h
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
-	d3dcaps.h
apiname:
-	D3DTRANSFORMCAPS
product: Windows
targetos: Windows
req.typenames: D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
---

# _D3DTRANSFORMCAPS structure


## -description



   Obsolete in DirectX 8.0 and later versions.
   

D3DTRANSFORMCAPS structure describes the transform capabilities of a device.


## -syntax


````
typedef struct _D3DTRANSFORMCAPS {
  DWORD dwSize;
  DWORD dwCaps;
} D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS;
````


## -struct-fields




#### - dwSize

Specifies the size, in bytes, of the D3DTRANSFORMCAPS structure. 


#### - dwCaps

Specifies flags describing the capabilities of the lighting module. The following flag is defined:

D3DTRANSFORMCAPS_CLIP 
<dl>
<dd>The device can do clipping operations while transforming.</dd>
</dl>



## -remarks


This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for DirectX 7.0 and earlier runtime compatibility. See <a href="https://msdn.microsoft.com/a03a7cbc-95be-4251-8e3a-bef4a093f03d">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

This structure is a member of the <a href="..\d3dhal\ns-d3dhal-_d3ddevicedesc_v1.md">D3DDEVICEDESC_V1</a> structure.



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3ddevicedesc_v1.md">D3DDEVICEDESC_V1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DTRANSFORMCAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

