---
UID: NS:d3dukmdt._D3DDDI_CREATEHWCONTEXTFLAGS
title: "_D3DDDI_CREATEHWCONTEXTFLAGS"
author: windows-driver-content
description: A structure used to create hardware context flags.
old-location: display\d3dddi_createhwcontextflags.htm
old-project: display
ms.assetid: 429A1C54-14F0-4E50-B0D6-BB73FCFD1904
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_CREATEHWCONTEXTFLAGS structure [Display Devices], _D3DDDI_CREATEHWCONTEXTFLAGS, D3DDDI_CREATEHWCONTEXTFLAGS, d3dukmdt/D3DDDI_CREATEHWCONTEXTFLAGS, display.d3dddi_createhwcontextflags
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
-	D3DDDI_CREATEHWCONTEXTFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_CREATEHWCONTEXTFLAGS
---

# _D3DDDI_CREATEHWCONTEXTFLAGS structure


## -description


A structure used to create hardware context flags.


## -syntax


````
typedef struct _D3DDDI_CREATEHWCONTEXTFLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} D3DDDI_CREATEHWCONTEXTFLAGS;
````


## -struct-fields




### -field Reserved

This value is reserved for system use.


### -field Value

This value is used to operate over the members collectively.

