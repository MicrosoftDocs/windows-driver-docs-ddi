---
UID: NS:d3dkmthk._D3DKMT_DESTROYHWCONTEXT
title: _D3DKMT_DESTROYHWCONTEXT
author: windows-driver-content
description: A structure holding information to destroy a hardware context.
old-location: display\d3dkmt_destroyhwcontext.htm
old-project: display
ms.assetid: DFFFE90A-C505-466A-B415-AA6C6352421B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_DESTROYHWCONTEXT, D3DKMT_DESTROYHWCONTEXT
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
req.alt-api: D3DKMT_DESTROYHWCONTEXT
req.alt-loc: d3dkmthk.h
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



## -remarks
