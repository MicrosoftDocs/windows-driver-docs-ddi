---
UID: NS:d3dkmddi._DXGK_PRESENTMULTIPLANEOVERLAYINFO
title: "_DXGK_PRESENTMULTIPLANEOVERLAYINFO"
author: windows-driver-content
description: Specifies info on a VidPN input and an overlay plane to display.
old-location: display\dxgk_presentmultiplaneoverlayinfo.htm
old-project: display
ms.assetid: b9cc78f3-b8b5-4a54-87b2-321b75ed9a21
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_PRESENTMULTIPLANEOVERLAYINFO structure [Display Devices], _DXGK_PRESENTMULTIPLANEOVERLAYINFO, display.dxgk_presentmultiplaneoverlayinfo, d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYINFO, DXGK_PRESENTMULTIPLANEOVERLAYINFO
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_PRESENTMULTIPLANEOVERLAYINFO
product: Windows
targetos: Windows
req.typenames: DXGK_PRESENTMULTIPLANEOVERLAYINFO
---

# _DXGK_PRESENTMULTIPLANEOVERLAYINFO structure


## -description


Specifies info on a VidPN input and an overlay plane to display.


## -syntax


````
typedef struct _DXGK_PRESENTMULTIPLANEOVERLAYINFO {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID    VidPnSourceId;
  UINT                              PlaneListCount;
  DXGK_PRESENTMULTIPLANEOVERLAYLIST *pPlaneList;
} DXGK_PRESENTMULTIPLANEOVERLAYINFO;
````


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field PlaneListCount

[in] The number of overlay planes that are available to display.


### -field pPlaneList

[in] A pointer to a structure of type <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentmultiplaneoverlaylist.md">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a> that describes the overlay plane to display.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentmultiplaneoverlaylist.md">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PRESENTMULTIPLANEOVERLAYINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

