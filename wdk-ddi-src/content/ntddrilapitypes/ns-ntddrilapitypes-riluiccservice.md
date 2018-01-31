---
UID: NS:ntddrilapitypes.RILUICCSERVICE
title: RILUICCSERVICE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccservice.htm
old-project: netvista
ms.assetid: 67c8abef-c920-4bc4-8216-8b6026a1962d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILUICCSERVICE, netvista.riluiccservice, RILUICCSERVICE structure [Network Drivers Starting with Windows Vista], *LPRILUICCSERVICE, RILUICCSERVICE
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
-	RILUICCSERVICE
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCSERVICE, RILUICCSERVICE"
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




#### - hUiccApp



#### - dwService


