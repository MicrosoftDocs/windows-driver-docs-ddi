---
UID: NS:d3dhal._D3DHAL_DP2CREATELIGHT
title: "_D3DHAL_DP2CREATELIGHT"
author: windows-driver-content
description: The D3DHAL_DP2CREATELIGHT structure is used to create a light for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createlight.htm
old-project: display
ms.assetid: 26dc353a-13e0-4408-b30f-4a9086cd7b9a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dhal_dp2createlight, _D3DHAL_DP2CREATELIGHT, d3dhal/D3DHAL_DP2CREATELIGHT, *LPD3DHAL_DP2CREATELIGHT, D3DHAL_DP2CREATELIGHT structure [Display Devices], D3DHAL_DP2CREATELIGHT, d3dstrct_8cbc2e0d-9728-407d-a860-b9460b33e837.xml, d3dhal/LPD3DHAL_DP2CREATELIGHT, LPD3DHAL_DP2CREATELIGHT, LPD3DHAL_DP2CREATELIGHT structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
-	d3dhal.h
apiname:
-	D3DHAL_DP2CREATELIGHT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATELIGHT
---

# _D3DHAL_DP2CREATELIGHT structure


## -description


The D3DHAL_DP2CREATELIGHT structure is used to create a light for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2CREATELIGHT {
  DWORD dwIndex;
} D3DHAL_DP2CREATELIGHT, *LPD3DHAL_DP2CREATELIGHT;
````


## -struct-fields




### -field dwIndex

Specifies the index of the light being created.


## -remarks


The D3DHAL_DP2CREATELIGHT structure is used to hold the index into the light array. The driver should enlarge its light array as necessary to accommodate at least as many lights as specified by the index.



## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATELIGHT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

