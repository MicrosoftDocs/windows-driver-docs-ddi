---
UID: NS:rilapitypes.RILMESSAGESTORAGEFULL
title: RILMESSAGESTORAGEFULL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagestoragefull_2.htm
old-project: netvista
ms.assetid: fa0e5c57-7ceb-442d-95ea-971824c88298
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL structure [Network Drivers Starting with Windows Vista], netvista.rilmessagestoragefull_2, rilapitypes/RILMESSAGESTORAGEFULL"
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
-	RILMESSAGESTORAGEFULL
product: Windows
targetos: Windows
req.typenames: RILMESSAGESTORAGEFULL, *LPRILMESSAGESTORAGEFULL
req.product: Windows 10 or later.
---

# RILMESSAGESTORAGEFULL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMESSAGESTORAGEFULL {
  DWORD     cbSize;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
} RILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL;
````


## -struct-fields




### -field cbSize


### -field dwExecutor


### -field hUiccApp

