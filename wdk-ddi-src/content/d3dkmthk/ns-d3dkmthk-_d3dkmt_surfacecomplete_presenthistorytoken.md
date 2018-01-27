---
UID: NS:d3dkmthk._D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN
title: _D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN
author: windows-driver-content
description: A structure used to present the history token for a surface.
old-location: display\d3dkmt_surfacecomplete_presenthistorytoken.htm
old-project: display
ms.assetid: AF58684E-3516-48F9-B771-63701C00645F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_surfacecomplete_presenthistorytoken, D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN structure [Display Devices], _D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN, D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN
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
-	D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN
---

# _D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN structure


## -description


A structure used to present the history token for a surface.


## -syntax


````
typedef struct _D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN {
  ULONG64 hLogicalSurface;
} D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN;
````


## -struct-fields




### -field hLogicalSurface

The logical surface that the token is being presented for.

