---
UID: NS:ntddrilapitypes.RILPHONEBOOKREADYSTATE
title: RILPHONEBOOKREADYSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookreadystate.htm
old-project: netvista
ms.assetid: cd71234b-4b46-4b7b-953b-32e6f014af03
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilphonebookreadystate, *LPRILPHONEBOOKREADYSTATE, ntddrilapitypes/RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE structure [Network Drivers Starting with Windows Vista]
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
-	RILPHONEBOOKREADYSTATE
product: Windows
targetos: Windows
req.typenames: "*LPRILPHONEBOOKREADYSTATE, RILPHONEBOOKREADYSTATE"
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


