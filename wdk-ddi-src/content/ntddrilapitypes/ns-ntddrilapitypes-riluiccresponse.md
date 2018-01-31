---
UID: NS:ntddrilapitypes.RILUICCRESPONSE
title: RILUICCRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccresponse.htm
old-project: netvista
ms.assetid: c584e508-b0f1-4809-808e-089e9a7fbcf9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.riluiccresponse, ntddrilapitypes/RILUICCRESPONSE, *LPRILUICCRESPONSE, RILUICCRESPONSE structure [Network Drivers Starting with Windows Vista], RILUICCRESPONSE
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
-	RILUICCRESPONSE
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCRESPONSE, RILUICCRESPONSE"
---

# RILUICCRESPONSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUICCRESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwStatusWord1;
  DWORD    dwStatusWord2;
  DWORD    dwResponseSize;
  BYTE [1] pbResponse;
} RILUICCRESPONSE, RILUICCRESPONSE;
````


## -struct-fields




#### - cbSize



#### - dwParams



#### - dwStatusWord1



#### - dwStatusWord2



#### - dwResponseSize



#### - pbResponse


