---
UID: NS:d3dumddi._D3DDDICB_SUBMITCOMMANDTOHWQUEUE
title: _D3DDDICB_SUBMITCOMMANDTOHWQUEUE
author: windows-driver-content
description: A structure that holds information to queue hardware flags.
old-location: display\d3dddicb_submitcommandtohwqueue.htm
old-project: display
ms.assetid: 5B650831-7AD7-4FEA-AC31-82F2B351BAD6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDICB_SUBMITCOMMANDTOHWQUEUE, D3DDDICB_SUBMITCOMMANDTOHWQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_SUBMITCOMMANDTOHWQUEUE
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDICB_SUBMITCOMMANDTOHWQUEUE
---

# _D3DDDICB_SUBMITCOMMANDTOHWQUEUE structure



## -description
A structure that holds information to queue hardware flags.



## -syntax

````
typedef struct _D3DDDICB_SUBMITCOMMANDTOHWQUEUE {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} D3DDDICB_SUBMITCOMMANDTOHWQUEUE;
````


## -struct-fields

### -field Reserved

This value is reserved for system use.


### -field Value

The combined UINT used to operate over the values.


## -remarks
