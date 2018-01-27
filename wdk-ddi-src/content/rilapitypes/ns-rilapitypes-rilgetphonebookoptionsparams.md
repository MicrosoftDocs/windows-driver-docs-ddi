---
UID: NS:rilapitypes.RILGETPHONEBOOKOPTIONSPARAMS
title: RILGETPHONEBOOKOPTIONSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetphonebookoptionsparams_2.htm
old-project: netvista
ms.assetid: ca82e408-6b22-4b0b-ac44-0650d3890674
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILGETPHONEBOOKOPTIONSPARAMS, rilapitypes/RILGETPHONEBOOKOPTIONSPARAMS, netvista.rilgetphonebookoptionsparams_2, RILGETPHONEBOOKOPTIONSPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILGETPHONEBOOKOPTIONSPARAMS
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
-	RILGETPHONEBOOKOPTIONSPARAMS
product: Windows
targetos: Windows
req.typenames: *LPRILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS
req.product: Windows 10 or later.
---

# RILGETPHONEBOOKOPTIONSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETPHONEBOOKOPTIONSPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
} RILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS;
````


## -struct-fields




### -field hUiccApp



### -field dwStoreLocation


