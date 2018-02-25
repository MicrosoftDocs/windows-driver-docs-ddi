---
UID: NS:d3d12umddi.D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030
title: D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030
author: windows-driver-content
description: Opens a protected resource session.
old-location: display\d3d12ddiarg-open-protected-resource-session-0030.htm
old-project: display
ms.assetid: d5f0a089-c6cb-444d-a959-ee8a5a024ea7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030, D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 structure [Display Devices], E, G, I, N, O, P, R, S, T, U, _, d3d12umddi/D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030, display.d3d12ddiarg-open-protected-resource-session-0030"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
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
-	d3d12umddi.h
apiname:
-	D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030
---

# D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 structure


## -description


Opens a protected resource session.


## -syntax


````
typedef struct _D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 {
  CONST VOID *  pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030, D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030;
````


## -struct-fields




### -field pPrivateDriverData

The private driver data.


### -field PrivateDriverDataSize

The private driver data size.

