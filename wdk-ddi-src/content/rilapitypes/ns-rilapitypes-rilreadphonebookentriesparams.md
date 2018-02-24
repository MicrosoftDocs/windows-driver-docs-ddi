---
UID: NS:rilapitypes.RILREADPHONEBOOKENTRIESPARAMS
title: RILREADPHONEBOOKENTRIESPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilreadphonebookentriesparams_2.htm
old-project: netvista
ms.assetid: 4cf1b9ab-0082-4ad3-9fd5-a29b51ca6bc0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILREADPHONEBOOKENTRIESPARAMS, rilapitypes/RILREADPHONEBOOKENTRIESPARAMS, *LPRILREADPHONEBOOKENTRIESPARAMS, RILREADPHONEBOOKENTRIESPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilreadphonebookentriesparams_2
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
-	RILREADPHONEBOOKENTRIESPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILREADPHONEBOOKENTRIESPARAMS, RILREADPHONEBOOKENTRIESPARAMS"
req.product: Windows 10 or later.
---

# RILREADPHONEBOOKENTRIESPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILREADPHONEBOOKENTRIESPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  DWORD                       dwStartIndex;
  DWORD                       dwEndIndex;
} RILREADPHONEBOOKENTRIESPARAMS, RILREADPHONEBOOKENTRIESPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwStoreLocation


### -field dwStartIndex


### -field dwEndIndex

