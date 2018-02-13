---
UID: NS:d3dkmthk._D3DKMT_PRESENT_RGNS
title: "_D3DKMT_PRESENT_RGNS"
author: windows-driver-content
description: Specifies dirty and move regions in a present operation.
old-location: display\d3dkmt_present_rgns.htm
old-project: display
ms.assetid: 90ae3382-0a2d-46cf-89e6-2148f0cbfc83
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_PRESENT_RGNS, d3dkmthk/D3DKMT_PRESENT_RGNS, _D3DKMT_PRESENT_RGNS, display.d3dkmt_present_rgns, D3DKMT_PRESENT_RGNS structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
apiname:
-	D3DKMT_PRESENT_RGNS
product: Windows
targetos: Windows
req.typenames: D3DKMT_PRESENT_RGNS
---

# _D3DKMT_PRESENT_RGNS structure


## -description


Specifies dirty and move regions in a present operation.


## -syntax


````
typedef struct _D3DKMT_PRESENT_RGNS {
  UINT                   DirtyRectCount;
  const RECT             *pDirtyRects;
  UINT                   MoveRectCount;
  const D3DKMT_MOVE_RECT *pMoveRects;
} D3DKMT_PRESENT_RGNS;
````


## -struct-fields




### -field DirtyRectCount

The number of dirty rectangles.


### -field pDirtyRects

A pointer to an array of dirty rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s).


### -field MoveRectCount

The number of move rectangles.


### -field pMoveRects

A pointer to an array of move rectangles (<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>s).


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_PRESENT_RGNS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

