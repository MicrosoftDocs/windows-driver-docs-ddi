---
UID: NS:rilapitypes.RILPHONEBOOKREADYSTATE
title: RILPHONEBOOKREADYSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookreadystate_2.htm
old-project: netvista
ms.assetid: 2193f73d-c21c-430d-8535-790fdea86366
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilphonebookreadystate_2, *LPRILPHONEBOOKREADYSTATE, rilapitypes/RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE structure [Network Drivers Starting with Windows Vista]
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
-	RILPHONEBOOKREADYSTATE
product: Windows
targetos: Windows
req.typenames: "*LPRILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE"
req.product: Windows 10 or later.
---

# RILPHONEBOOKREADYSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPHONEBOOKREADYSTATE {
  DWORD     cbSize;
  HUICCAPP  hUiccApp;
  DWORD     dwStoreLocations;
} RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE;
````


## -struct-fields




### -field cbSize



### -field hUiccApp



### -field dwStoreLocations


