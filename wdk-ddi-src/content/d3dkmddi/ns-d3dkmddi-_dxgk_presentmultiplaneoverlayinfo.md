---
UID: NS:d3dkmddi._DXGK_PRESENTMULTIPLANEOVERLAYINFO
title: "_DXGK_PRESENTMULTIPLANEOVERLAYINFO"
author: windows-driver-content
description: Specifies info on a VidPN input and an overlay plane to display.
old-location: display\dxgk_presentmultiplaneoverlayinfo.htm
ms.assetid: b9cc78f3-b8b5-4a54-87b2-321b75ed9a21
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_PRESENTMULTIPLANEOVERLAYINFO, DXGK_PRESENTMULTIPLANEOVERLAYINFO structure [Display Devices], _DXGK_PRESENTMULTIPLANEOVERLAYINFO, d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYINFO, display.dxgk_presentmultiplaneoverlayinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dkmddi.h
api_name:
-	DXGK_PRESENTMULTIPLANEOVERLAYINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_PRESENTMULTIPLANEOVERLAYINFO
---

# _DXGK_PRESENTMULTIPLANEOVERLAYINFO structure


## -description


Specifies info on a VidPN input and an overlay plane to display.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field PlaneListCount

[in] The number of overlay planes that are available to display.


### -field pPlaneList

[in] A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh780312">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a> that describes the overlay plane to display.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780312">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a>
 

 

