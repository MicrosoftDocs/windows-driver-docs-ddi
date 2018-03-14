---
UID: NE:filterpipeline.__MIDL___MIDL_itf_filterpipeline_0000_0000_0001
title: "__MIDL___MIDL_itf_filterpipeline_0000_0000_0001"
author: windows-driver-content
description: The ExpsCompressionOptions enumeration describes compression options for an XPS part.
old-location: print\expscompressionoptions.htm
old-project: print
ms.assetid: 7df53803-4e01-4d00-b7a4-2f2d1dde5ad8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Compression_Fast, Compression_Normal, Compression_NotCompressed, Compression_Small, EXpsCompressionOptions, EXpsCompressionOptions enumeration [Print Devices], __MIDL___MIDL_itf_filterpipeline_0000_0000_0001, filterpipeline/Compression_Fast, filterpipeline/Compression_Normal, filterpipeline/Compression_NotCompressed, filterpipeline/Compression_Small, filterpipeline/EXpsCompressionOptions, filterpipeline_eb934659-a4bd-4063-b0a7-f4011998c0ec.xml, print.expscompressionoptions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	filterpipeline.h
api_name:
-	EXpsCompressionOptions
product: Windows
targetos: Windows
req.typenames: EXpsCompressionOptions
---

# __MIDL___MIDL_itf_filterpipeline_0000_0000_0001 enumeration


## -description


The ExpsCompressionOptions enumeration describes compression options for an XPS part.


## -syntax


````
typedef enum  { 
  Compression_NotCompressed,
  Compression_Normal,
  Compression_Small,
  Compression_Fast
} EXpsCompressionOptions;
````


## -enum-fields




### -field Compression_NotCompressed

The part is not compressed.


### -field Compression_Normal

The part is compressed normally.


### -field Compression_Small

The compression for the part is optimized for size.


### -field Compression_Fast

The compression for the part is optimized for speed.

