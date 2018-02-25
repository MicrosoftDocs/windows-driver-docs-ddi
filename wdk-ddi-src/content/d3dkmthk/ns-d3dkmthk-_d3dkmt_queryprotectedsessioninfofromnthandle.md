---
UID: NS:d3dkmthk._D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
title: "_D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE"
author: windows-driver-content
description: Used to query information on the protected session.
old-location: display\d3dkmt-queryprotectedsessioninfofromnthandle.htm
old-project: display
ms.assetid: e08d27e7-e9b7-45e7-9bbd-dcb9aa8f85ed
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE structure [Display Devices], E, F, H, I, K, L, M, N, O, P, Q, R, S, T, U, Y, _, _D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, d3dkmthk/D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, display.d3dkmt-queryprotectedsessioninfofromnthandle"
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
-	D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
---

# _D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE structure


## -description


Used to query information on the protected session.


## -syntax


````
typedef struct _D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE {
  HANDLE     hNtHandle;
  const VOID *pPrivateDriverData;
  UINT       PrivateDriverDataSize;
  const VOID *pPrivateRuntimeData;
  UINT       PrivateRuntimeDataSize;
} D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE;
````


## -struct-fields




### -field hNtHandle

The protected NT session handle.


### -field pPrivateDriverData

The private driver data.


### -field PrivateDriverDataSize

The size of the private driver data.


### -field pPrivateRuntimeData

The private runtime data.


### -field PrivateRuntimeDataSize

The size of the private runtime data.

