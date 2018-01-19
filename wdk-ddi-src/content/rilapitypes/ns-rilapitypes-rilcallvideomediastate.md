---
UID: NS:rilapitypes.RILCALLVIDEOMEDIASTATE
title: RILCALLVIDEOMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallvideomediastate_2.htm
old-project: netvista
ms.assetid: f4d72de5-4e42-4229-b33e-8a0391f2f6cf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLVIDEOMEDIASTATE, RILCALLVIDEOMEDIASTATE, *LPRILCALLVIDEOMEDIASTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLVIDEOMEDIASTATE
req.alt-loc: rilapitypes.h
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
req.typenames: RILCALLVIDEOMEDIASTATE, *LPRILCALLVIDEOMEDIASTATE
req.product: Windows 10 or later.
---

# RILCALLVIDEOMEDIASTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLVIDEOMEDIASTATE {
  DWORD                  dwParams;
  RILCALLMEDIADIRECTION  dwPeerCapabilities;
  DWORD                  dwFlags;
  DWORD                  dwContextID;
} RILCALLVIDEOMEDIASTATE, RILCALLVIDEOMEDIASTATE;
````


## -struct-fields

### -field dwParams


### -field dwPeerCapabilities


### -field dwFlags


### -field dwContextID


## -remarks
