---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_INITIALIZE
title: _DXGKVGPU_ESCAPE_INITIALIZE
author: windows-driver-content
description: Used to initialize an escape.
old-location: display\dxgkvgpu_escape_initialize.htm
old-project: display
ms.assetid: 697F4A4C-349E-46E5-B891-215C4AFFC4B6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKVGPU_ESCAPE_INITIALIZE structure [Display Devices], _DXGKVGPU_ESCAPE_INITIALIZE, d3dukmdt/DXGKVGPU_ESCAPE_INITIALIZE, DXGKVGPU_ESCAPE_INITIALIZE, display.dxgkvgpu_escape_initialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dukmdt.h
apiname: 
-	DXGKVGPU_ESCAPE_INITIALIZE
product: Windows
targetos: Windows
req.typenames: DXGKVGPU_ESCAPE_INITIALIZE
---

# _DXGKVGPU_ESCAPE_INITIALIZE structure


## -description


Used to initialize an escape.


## -syntax


````
typedef struct _DXGKVGPU_ESCAPE_INITIALIZE {
  DXGKVGPU_ESCAPE_HEAD Header;
} DXGKVGPU_ESCAPE_INITIALIZE;
````


## -struct-fields




### -field Header

The header that is being operated over.

