---
UID: NS:rilapitypes.RILUICCSERVICE
title: RILUICCSERVICE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccservice_2.htm
old-project: netvista
ms.assetid: ffd61de0-652a-4174-a0d2-d53c28180ea5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCSERVICE, *LPRILUICCSERVICE, RILUICCSERVICE
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
req.alt-api: RILUICCSERVICE
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILUICCSERVICE, RILUICCSERVICE
req.product: Windows 10 or later.
---

# RILUICCSERVICE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCSERVICE {
  HUICCAPP               hUiccApp;
  RILUICCSERVICESERVICE  dwService;
} RILUICCSERVICE, RILUICCSERVICE;
````


## -struct-fields

### -field hUiccApp


### -field dwService


## -remarks
