---
UID: NS:rilapitypes.RILEMERGENCYNUMBER
title: RILEMERGENCYNUMBER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumber_2.htm
old-project: netvista
ms.assetid: 70759d23-b5ab-4c51-b73f-32021b9ae6fb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILEMERGENCYNUMBER, *LPRILEMERGENCYNUMBER, RILEMERGENCYNUMBER, RILEMERGENCYNUMBER structure [Network Drivers Starting with Windows Vista], netvista.rilemergencynumber_2
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
-	RILEMERGENCYNUMBER
product: Windows
targetos: Windows
req.typenames: "*LPRILEMERGENCYNUMBER, RILEMERGENCYNUMBER"
req.product: Windows 10 or later.
---

# RILEMERGENCYNUMBER structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILEMERGENCYNUMBER {
  DWORD                             cbSize;
  DWORD                             dwParams;
  DWORD                             dwExecutor;
  HUICCAPP                          hUiccApp;
  DWORD                             dwCategory;
  WCHAR [MAXLENGTH_EMERGENCYNUMBER] wszEmergencyNumber;
} RILEMERGENCYNUMBER, RILEMERGENCYNUMBER;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwExecutor



### -field hUiccApp



### -field dwCategory



### -field wszEmergencyNumber


