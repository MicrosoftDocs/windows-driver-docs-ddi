---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_RELEASE
title: _DXGKVGPU_ESCAPE_RELEASE
author: windows-driver-content
description: Indicates that an escape has been released.
old-location: display\dxgkvgpu_escape_release.htm
old-project: display
ms.assetid: 96BA0967-BA65-483D-9165-C7ADE05C0216
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkvgpu_escape_release, DXGKVGPU_ESCAPE_RELEASE, DXGKVGPU_ESCAPE_RELEASE structure [Display Devices], _DXGKVGPU_ESCAPE_RELEASE, d3dukmdt/DXGKVGPU_ESCAPE_RELEASE
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
-	DXGKVGPU_ESCAPE_RELEASE
product: Windows
targetos: Windows
req.typenames: DXGKVGPU_ESCAPE_RELEASE
---

# _DXGKVGPU_ESCAPE_RELEASE structure


## -description


Indicates that an escape has been released.


## -syntax


````
typedef struct _DXGKVGPU_ESCAPE_RELEASE {
  DXGKVGPU_ESCAPE_HEAD Header;
} DXGKVGPU_ESCAPE_RELEASE;
````


## -struct-fields




### -field Header

The header that is being operated on.

