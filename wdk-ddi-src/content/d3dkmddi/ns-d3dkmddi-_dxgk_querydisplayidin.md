---
UID: NS:d3dkmddi._DXGK_QUERYDISPLAYIDIN
title: _DXGK_QUERYDISPLAYIDIN
author: windows-driver-content
description: Used to query a display ID.
old-location: display\dxgk_querydisplayidin.htm
old-project: display
ms.assetid: C7A2CECA-AAE5-4804-92FF-C47984BA38AF
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_QUERYDISPLAYIDIN, display.dxgk_querydisplayidin, DXGK_QUERYDISPLAYIDIN structure [Display Devices], DXGK_QUERYDISPLAYIDIN, d3dkmddi/DXGK_QUERYDISPLAYIDIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_QUERYDISPLAYIDIN
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYDISPLAYIDIN
---

# _DXGK_QUERYDISPLAYIDIN structure


## -description


Used to query a display ID.


## -syntax


````
typedef struct _DXGK_QUERYDISPLAYIDIN {
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
} DXGK_QUERYDISPLAYIDIN;
````


## -struct-fields




### -field TargetId

The ID being queried.

