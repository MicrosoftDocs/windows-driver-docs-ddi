---
UID: NS:d3dkmthk._D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN
title: "_D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: Identifies a composition swap chain present-history operation. This type of presentation is used for Extensible Application Markup Language (XAML)-based apps.
old-location: display\d3dkmt_composition_presenthistorytoken.htm
old-project: display
ms.assetid: F3F2DE77-9FC5-4AC1-B857-51B51557108E
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, C, D, D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN, D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN structure [Display Devices], E, H, I, K, M, N, O, P, R, S, T, Y, _, _D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN, display.d3dkmt_composition_presenthistorytoken"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dkmthk.h
apiname:
-	D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN
---

# _D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN structure


## -description


Identifies a composition swap chain present-history operation. This type of presentation is used for Extensible Application Markup Language (XAML)-based apps.


## -syntax


````
typedef struct _D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN {
  ULONG64 hPrivateData;
} D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN;
````


## -struct-fields




### -field hPrivateData

A driver-resident private data structure that identifies a composition swap chain present-history operation.

