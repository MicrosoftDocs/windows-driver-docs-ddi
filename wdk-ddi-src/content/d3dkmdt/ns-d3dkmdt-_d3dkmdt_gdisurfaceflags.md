---
UID: NS:d3dkmdt._D3DKMDT_GDISURFACEFLAGS
title: "_D3DKMDT_GDISURFACEFLAGS"
author: windows-driver-content
description: The D3DKMDT_GDISURFACEFLAGS structure is reserved for system use. Do not use it in your driver.
old-location: display\d3dkmdt_gdisurfaceflags.htm
old-project: display
ms.assetid: ce6e1ca4-7a44-46ee-a5ac-33e143ce6377
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DKMDT_GDISURFACEFLAGS, D3DKMDT_GDISURFACEFLAGS structure [Display Devices], DmStructs_6d5ae8f4-0155-41d5-b558-a229f68ffa99.xml, E, F, G, I, K, L, M, R, S, T, U, _, _D3DKMDT_GDISURFACEFLAGS, d3dkmdt/D3DKMDT_GDISURFACEFLAGS, display.d3dkmdt_gdisurfaceflags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	d3dkmdt.h
apiname:
-	D3DKMDT_GDISURFACEFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMDT_GDISURFACEFLAGS
---

# _D3DKMDT_GDISURFACEFLAGS structure


## -description


The D3DKMDT_GDISURFACEFLAGS structure is reserved for system use. Do not use it in your driver.


## -syntax


````
typedef struct _D3DKMDT_GDISURFACEFLAGS {
  union {
    struct {
      UINT Stereo           :1;
      UINT Reserved  :31;
    };
  };
  UINT Value;
} D3DKMDT_GDISURFACEFLAGS;
````


## -struct-fields




### -field Reserved

Reserved for system use.


#### - Stereo

Reserved for system use.


#### - Value

Reserved for system use.

