---
UID: NS:rilapitypes.RILDELETEPHONEBOOKENTRYPARAMS
title: RILDELETEPHONEBOOKENTRYPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeletephonebookentryparams_2.htm
old-project: netvista
ms.assetid: 33e64f4f-a632-47d0-a133-f64d6f4b1cda
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILDELETEPHONEBOOKENTRYPARAMS, ,, A, B, D, E, H, I, K, L, M, N, O, P, R, RILDELETEPHONEBOOKENTRYPARAMS, RILDELETEPHONEBOOKENTRYPARAMS structure [Network Drivers Starting with Windows Vista], S, T, Y, netvista.rildeletephonebookentryparams_2, rilapitypes/RILDELETEPHONEBOOKENTRYPARAMS"
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
-	RILDELETEPHONEBOOKENTRYPARAMS
product: Windows
targetos: Windows
req.typenames: RILDELETEPHONEBOOKENTRYPARAMS, *LPRILDELETEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RILDELETEPHONEBOOKENTRYPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILDELETEPHONEBOOKENTRYPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  DWORD                       dwIndex;
  BOOL                        fHasLockVerification;
  RILUICCLOCKCREDENTIAL       lockVerification;
} RILDELETEPHONEBOOKENTRYPARAMS, RILDELETEPHONEBOOKENTRYPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwStoreLocation


### -field dwIndex


### -field fHasLockVerification


### -field lockVerification

