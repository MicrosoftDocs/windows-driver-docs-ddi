---
UID: NS:ntddrilapitypes.RILWRITEMSGPARAMS
title: RILWRITEMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwritemsgparams.htm
old-project: netvista
ms.assetid: d66d63cd-ec34-4749-9ed9-38ee6d962ea5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILWRITEMSGPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILWRITEMSGPARAMS, ntddrilapitypes/RILWRITEMSGPARAMS, netvista.rilwritemsgparams, RILWRITEMSGPARAMS
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
-	RILWRITEMSGPARAMS
product: Windows
targetos: Windows
req.typenames: RILWRITEMSGPARAMS, *LPRILWRITEMSGPARAMS
---

# RILWRITEMSGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILWRITEMSGPARAMS {
  HUICCAPP          hUiccApp;
  RILMESSAGE        rmMessage;
  RILMESSAGESTATUS  dwStatus;
} RILWRITEMSGPARAMS, RILWRITEMSGPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field rmMessage


### -field dwStatus

