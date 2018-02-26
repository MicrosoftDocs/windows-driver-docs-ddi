---
UID: NS:d3dkmthk._D3DKMT_QUERYPROTECTEDSESSIONSTATUS
title: "_D3DKMT_QUERYPROTECTEDSESSIONSTATUS"
author: windows-driver-content
description: Used to query the status of the protected session.
old-location: display\d3dkmt-queryprotectedsessionstatus.htm
old-project: display
ms.assetid: c49b1c12-8757-4d15-807d-fdb963746810
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DKMT_QUERYPROTECTEDSESSIONSTATUS, D3DKMT_QUERYPROTECTEDSESSIONSTATUS structure [Display Devices], E, I, K, M, N, O, P, Q, R, S, T, U, Y, _, _D3DKMT_QUERYPROTECTEDSESSIONSTATUS, d3dkmthk/D3DKMT_QUERYPROTECTEDSESSIONSTATUS, display.d3dkmt-queryprotectedsessionstatus"
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
-	D3DKMT_QUERYPROTECTEDSESSIONSTATUS
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYPROTECTEDSESSIONSTATUS
---

# _D3DKMT_QUERYPROTECTEDSESSIONSTATUS structure


## -description


Used to query the status of the protected session.


## -syntax


````
typedef struct _D3DKMT_QUERYPROTECTEDSESSIONSTATUS {
  D3DKMT_HANDLE                   hHandle;
  D3DKMT_PROTECTED_SESSION_STATUS Status;
} D3DKMT_QUERYPROTECTEDSESSIONSTATUS;
````


## -struct-fields




### -field hHandle

The handle of the protected session.


### -field Status

The status of the protected session.

