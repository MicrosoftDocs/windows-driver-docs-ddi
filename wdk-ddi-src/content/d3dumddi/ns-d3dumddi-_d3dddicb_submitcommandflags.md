---
UID: NS:d3dumddi._D3DDDICB_SUBMITCOMMANDFLAGS
title: _D3DDDICB_SUBMITCOMMANDFLAGS
author: windows-driver-content
description: D3DDDICB_SUBMITCOMMANDFLAGS is used to indicate how to process command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dddicb_submitcommandflags.htm
old-project: display
ms.assetid: 415255A8-4D43-4677-B4B3-0425D6D57933
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDICB_SUBMITCOMMANDFLAGS, D3DDDICB_SUBMITCOMMANDFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_SUBMITCOMMANDFLAGS
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
req.typenames: D3DDDICB_SUBMITCOMMANDFLAGS
---

# _D3DDDICB_SUBMITCOMMANDFLAGS structure



## -description
<b>D3DDDICB_SUBMITCOMMANDFLAGS</b> is used to indicate how to process command buffers on contexts that support graphics processing unit (GPU) virtual addressing.



## -syntax

````
typedef struct _D3DDDICB_SUBMITCOMMANDFLAGS {
  union {
    struct {
      UINT NullRendering  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DDDICB_SUBMITCOMMANDFLAGS;
````


## -struct-fields

### -field NullRendering

Indicates  whether the associated  command buffers should be processed. When set, the command buffers should not be processed. This flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations.



Setting this member is equivalent to setting the first bit of the 32-bit Value member (0x00000001).



### -field Reserved

This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

The consolidated value of the bit-field members in this structure.


## -remarks
