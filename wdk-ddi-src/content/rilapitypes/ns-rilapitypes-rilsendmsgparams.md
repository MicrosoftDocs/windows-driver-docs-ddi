---
UID: NS:rilapitypes.RILSENDMSGPARAMS
title: RILSENDMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgparams_2.htm
old-project: netvista
ms.assetid: db2eeb43-710a-4be6-8d9f-49809ff70057
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSENDMSGPARAMS, RILSENDMSGPARAMS, RILSENDMSGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendmsgparams_2, rilapitypes/RILSENDMSGPARAMS"
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
-	RILSENDMSGPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDMSGPARAMS, *LPRILSENDMSGPARAMS
req.product: Windows 10 or later.
---

# RILSENDMSGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSENDMSGPARAMS {
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  RILMESSAGE  rmMessage;
  DWORD       dwOptions;
} RILSENDMSGPARAMS, RILSENDMSGPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field hUiccApp


### -field rmMessage


### -field dwOptions

