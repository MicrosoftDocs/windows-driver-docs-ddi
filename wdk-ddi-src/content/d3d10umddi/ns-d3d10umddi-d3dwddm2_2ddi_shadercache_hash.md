---
UID: NS:d3d10umddi.D3DWDDM2_2DDI_SHADERCACHE_HASH
title: D3DWDDM2_2DDI_SHADERCACHE_HASH
author: windows-driver-content
description: Contains a hash value for a shader cache.
old-location: display\d3dwddm2_2ddi_shadercache_hash.htm
old-project: display
ms.assetid: 1024FF58-7758-473A-8B1F-9CE184B9667A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM2_2DDI_SHADERCACHE_HASH, display.d3dwddm2_2ddi_shadercache_hash, D3DWDDM2_2DDI_SHADERCACHE_HASH, D3DWDDM2_2DDI_SHADERCACHE_HASH structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
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
-	d3d10umddi.h
apiname: 
-	D3DWDDM2_2DDI_SHADERCACHE_HASH
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_2DDI_SHADERCACHE_HASH
---

# D3DWDDM2_2DDI_SHADERCACHE_HASH structure


## -description


Contains a hash value for a shader cache.


## -syntax


````
typedef struct D3DWDDM2_2DDI_SHADERCACHE_HASH {
  BYTE Hash[16];
} D3DWDDM2_2DDI_SHADERCACHE_HASH;
````


## -struct-fields




### -field Hash

A hash value.

