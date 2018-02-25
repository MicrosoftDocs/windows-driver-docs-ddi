---
UID: NS:rilapitypes.RILSETUICCLOCKENABLEDPARAMS
title: RILSETUICCLOCKENABLEDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetuicclockenabledparams_2.htm
old-project: netvista
ms.assetid: c29aa1f0-d274-4782-9b56-31a84e2686e4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSETUICCLOCKENABLEDPARAMS, ,, A, B, C, D, E, I, K, L, M, N, O, P, R, RILSETUICCLOCKENABLEDPARAMS, RILSETUICCLOCKENABLEDPARAMS structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.rilsetuicclockenabledparams_2, rilapitypes/RILSETUICCLOCKENABLEDPARAMS"
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
-	RILSETUICCLOCKENABLEDPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETUICCLOCKENABLEDPARAMS, *LPRILSETUICCLOCKENABLEDPARAMS
req.product: Windows 10 or later.
---

# RILSETUICCLOCKENABLEDPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSETUICCLOCKENABLEDPARAMS {
  RILUICCLOCKCREDENTIAL  lockCredential;
  BOOL                   fEnable;
} RILSETUICCLOCKENABLEDPARAMS, RILSETUICCLOCKENABLEDPARAMS;
````


## -struct-fields




### -field lockCredential


### -field fEnable

