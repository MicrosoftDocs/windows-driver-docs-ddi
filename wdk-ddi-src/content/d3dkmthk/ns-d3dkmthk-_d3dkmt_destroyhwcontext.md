---
UID: NS:d3dkmthk._D3DKMT_DESTROYHWCONTEXT
title: "_D3DKMT_DESTROYHWCONTEXT"
author: windows-driver-content
description: A structure holding information to destroy a hardware context.
old-location: display\d3dkmt_destroyhwcontext.htm
old-project: display
ms.assetid: DFFFE90A-C505-466A-B415-AA6C6352421B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_DESTROYHWCONTEXT, D3DKMT_DESTROYHWCONTEXT structure [Display Devices], _D3DKMT_DESTROYHWCONTEXT, d3dkmthk/D3DKMT_DESTROYHWCONTEXT, display.d3dkmt_destroyhwcontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	D3DKMT_DESTROYHWCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYHWCONTEXT
---

# _D3DKMT_DESTROYHWCONTEXT structure


## -description


A structure holding information to destroy a hardware context.


## -syntax


````
typedef struct _D3DKMT_DESTROYHWCONTEXT {
  D3DKMT_HANDLE hHwContext;
} D3DKMT_DESTROYHWCONTEXT;
````


## -struct-fields




### -field hHwContext

A handle that identifies the context being destroyed.


