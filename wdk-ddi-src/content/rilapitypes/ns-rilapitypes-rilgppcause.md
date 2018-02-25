---
UID: NS:rilapitypes.RILGPPCAUSE
title: RILGPPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgppcause_2.htm
old-project: netvista
ms.assetid: 33e54af8-4ff1-44e2-926f-8f045e15b000
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILGPPCAUSE, ,, A, C, E, G, I, L, P, R, RILGPPCAUSE, RILGPPCAUSE structure [Network Drivers Starting with Windows Vista], S, U, netvista.rilgppcause_2, rilapitypes/RILGPPCAUSE"
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
-	rilapitypes.h
apiname:
-	RILGPPCAUSE
product: Windows
targetos: Windows
req.typenames: RILGPPCAUSE, *LPRILGPPCAUSE
req.product: Windows 10 or later.
---

# RILGPPCAUSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGPPCAUSE {
  DWORD  dwLocation;
  DWORD  dwCauseValue;
} RILGPPCAUSE, RILGPPCAUSE;
````


## -struct-fields




### -field dwLocation


### -field dwCauseValue

