---
UID: NS:rilapitypes.RILUICCLOCKCREDENTIAL
title: RILUICCLOCKCREDENTIAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockcredential_2.htm
old-project: netvista
ms.assetid: bb7b3075-c424-4a8b-bff9-64cdb85218a2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL, *LPRILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL structure [Network Drivers Starting with Windows Vista], netvista.riluicclockcredential_2
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
-	RILUICCLOCKCREDENTIAL
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKCREDENTIAL, *LPRILUICCLOCKCREDENTIAL
req.product: Windows 10 or later.
---

# RILUICCLOCKCREDENTIAL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCLOCKCREDENTIAL {
  RILUICCLOCK               rilUiccLock;
  char [MAXLENGTH_PASSWORD] szPassword;
} RILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL;
````


## -struct-fields




### -field rilUiccLock



### -field szPassword


