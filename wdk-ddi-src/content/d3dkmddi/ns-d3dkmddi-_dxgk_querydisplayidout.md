---
UID: NS:d3dkmddi._DXGK_QUERYDISPLAYIDOUT
title: "_DXGK_QUERYDISPLAYIDOUT"
author: windows-driver-content
description: Used to query a display ID.
old-location: display\dxgk_querydisplayidout.htm
old-project: display
ms.assetid: BF528089-0194-4A3F-B8BA-85F80974C4C2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_QUERYDISPLAYIDOUT, d3dkmddi/DXGK_QUERYDISPLAYIDOUT, display.dxgk_querydisplayidout, DXGK_QUERYDISPLAYIDOUT, DXGK_QUERYDISPLAYIDOUT structure [Display Devices]"
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
-	DXGK_QUERYDISPLAYIDOUT
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYDISPLAYIDOUT
---

# _DXGK_QUERYDISPLAYIDOUT structure


## -description


Used to query a display ID.


## -syntax


````
typedef struct _DXGK_QUERYDISPLAYIDOUT {
  UINT Length;
  BYTE *pDescriptor;
} DXGK_QUERYDISPLAYIDOUT;
````


## -struct-fields




### -field Length

The length of the Display ID.


### -field pDescriptor

A pointer to the descriptor of the ID.

