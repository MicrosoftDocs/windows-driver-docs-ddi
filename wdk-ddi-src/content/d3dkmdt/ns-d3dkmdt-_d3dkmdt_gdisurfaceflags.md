---
UID: NS:d3dkmdt._D3DKMDT_GDISURFACEFLAGS
title: "_D3DKMDT_GDISURFACEFLAGS"
author: windows-driver-content
description: The D3DKMDT_GDISURFACEFLAGS structure is reserved for system use. Do not use it in your driver.
old-location: display\d3dkmdt_gdisurfaceflags.htm
old-project: display
ms.assetid: ce6e1ca4-7a44-46ee-a5ac-33e143ce6377
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmdt_gdisurfaceflags, _D3DKMDT_GDISURFACEFLAGS, DmStructs_6d5ae8f4-0155-41d5-b558-a229f68ffa99.xml, D3DKMDT_GDISURFACEFLAGS, D3DKMDT_GDISURFACEFLAGS structure [Display Devices], d3dkmdt/D3DKMDT_GDISURFACEFLAGS
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


### -field Value

Reserved for system use.


#### - Stereo

Reserved for system use.

