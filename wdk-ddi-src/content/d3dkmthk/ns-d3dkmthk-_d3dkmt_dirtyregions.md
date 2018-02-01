---
UID: NS:d3dkmthk._D3DKMT_DIRTYREGIONS
title: "_D3DKMT_DIRTYREGIONS"
author: windows-driver-content
description: The D3DKMT_DIRTYREGIONS structure describes active rectangles (dirty regions) of a surface.
old-location: display\d3dkmt_dirtyregions.htm
old-project: display
ms.assetid: 53565c01-9e6f-4ade-8c4a-2a4dbe7d48c7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_DIRTYREGIONS, D3DKMT_DIRTYREGIONS structure [Display Devices], OpenGL_Structs_a6113f9d-8ffc-4e75-8366-8329ad6c114b.xml, D3DKMT_DIRTYREGIONS, display.d3dkmt_dirtyregions, d3dkmthk/D3DKMT_DIRTYREGIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DIRTYREGIONS is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
apiname:
-	D3DKMT_DIRTYREGIONS
product: Windows
targetos: Windows
req.typenames: D3DKMT_DIRTYREGIONS
---

# _D3DKMT_DIRTYREGIONS structure


## -description


The D3DKMT_DIRTYREGIONS structure describes active rectangles (dirty regions) of a surface. 


## -syntax


````
typedef struct _D3DKMT_DIRTYREGIONS {
  UINT NumRects;
  RECT Rects[D3DKMT_MAX_PRESENT_HISTORY_RECTS];
} D3DKMT_DIRTYREGIONS;
````


## -struct-fields




### -field NumRects

[in] The number of dirty regions in the array that the <b>Rects</b> member specifies. 


### -field Rects

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures that specifies the dirty regions of a surface.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DIRTYREGIONS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

