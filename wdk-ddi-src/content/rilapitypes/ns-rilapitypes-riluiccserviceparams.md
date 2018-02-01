---
UID: NS:rilapitypes.RILUICCSERVICEPARAMS
title: RILUICCSERVICEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccserviceparams_2.htm
old-project: netvista
ms.assetid: 56fba38d-6c5f-4b75-98b6-213a42f47bbb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.riluiccserviceparams_2, *LPRILUICCSERVICEPARAMS
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
-	RILUICCSERVICEPARAMS
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICEPARAMS, *LPRILUICCSERVICEPARAMS
req.product: Windows 10 or later.
---

# RILUICCSERVICEPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCSERVICEPARAMS {
  RILUICCSERVICE         service;
  BOOL                   fHasLockVerification;
  RILUICCLOCKCREDENTIAL  lockCredential;
  BOOL                   fEnable;
} RILUICCSERVICEPARAMS, RILUICCSERVICEPARAMS;
````


## -struct-fields




### -field service



### -field fHasLockVerification



### -field lockCredential



### -field fEnable


