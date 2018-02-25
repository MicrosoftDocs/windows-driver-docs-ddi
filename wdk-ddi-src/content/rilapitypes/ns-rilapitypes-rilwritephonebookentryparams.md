---
UID: NS:rilapitypes.RILWRITEPHONEBOOKENTRYPARAMS
title: RILWRITEPHONEBOOKENTRYPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwritephonebookentryparams_2.htm
old-project: netvista
ms.assetid: ae92f321-d6dc-4e48-8107-1a6fbd3bb15a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILWRITEPHONEBOOKENTRYPARAMS, ,, A, B, E, H, I, K, L, M, N, O, P, R, RILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS structure [Network Drivers Starting with Windows Vista], S, T, W, Y, netvista.rilwritephonebookentryparams_2, rilapitypes/RILWRITEPHONEBOOKENTRYPARAMS"
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
-	RILWRITEPHONEBOOKENTRYPARAMS
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RILWRITEPHONEBOOKENTRYPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILWRITEPHONEBOOKENTRYPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  BOOL                        fHasLockVerification;
  RILUICCLOCKCREDENTIAL       lockVerification;
  RILPHONEBOOKENTRY           pbEntry;
} RILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwStoreLocation


### -field fHasLockVerification


### -field lockVerification


### -field pbEntry

