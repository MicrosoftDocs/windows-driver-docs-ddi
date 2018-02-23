---
UID: NS:ntddrilapitypes.RILDELETEPHONEBOOKENTRYPARAMS
title: RILDELETEPHONEBOOKENTRYPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeletephonebookentryparams.htm
old-project: netvista
ms.assetid: 1a372468-2bad-44d4-a19a-d3b517b7ed7b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILDELETEPHONEBOOKENTRYPARAMS, RILDELETEPHONEBOOKENTRYPARAMS structure [Network Drivers Starting with Windows Vista], RILDELETEPHONEBOOKENTRYPARAMS, *LPRILDELETEPHONEBOOKENTRYPARAMS, netvista.rildeletephonebookentryparams
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILDELETEPHONEBOOKENTRYPARAMS
product: Windows
targetos: Windows
req.typenames: RILDELETEPHONEBOOKENTRYPARAMS, *LPRILDELETEPHONEBOOKENTRYPARAMS
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

