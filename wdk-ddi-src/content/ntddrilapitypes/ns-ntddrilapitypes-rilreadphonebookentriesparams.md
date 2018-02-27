---
UID: NS:ntddrilapitypes.RILREADPHONEBOOKENTRIESPARAMS
title: RILREADPHONEBOOKENTRIESPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilreadphonebookentriesparams.htm
old-project: netvista
ms.assetid: af74f94a-497a-4771-aee4-d1ba8d2f3ad9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILREADPHONEBOOKENTRIESPARAMS, RILREADPHONEBOOKENTRIESPARAMS, RILREADPHONEBOOKENTRIESPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilreadphonebookentriesparams, ntddrilapitypes/RILREADPHONEBOOKENTRIESPARAMS"
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
-	RILREADPHONEBOOKENTRIESPARAMS
product: Windows
targetos: Windows
req.typenames: RILREADPHONEBOOKENTRIESPARAMS, *LPRILREADPHONEBOOKENTRIESPARAMS
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

