---
UID: NS:rilapitypes.RILUICCRESPONSE
title: RILUICCRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccresponse_2.htm
old-project: netvista
ms.assetid: c3d3481e-a0db-492d-8fc3-6bdcfa26f4c4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCRESPONSE, RILUICCRESPONSE structure [Network Drivers Starting with Windows Vista], netvista.riluiccresponse_2, rilapitypes/RILUICCRESPONSE, *LPRILUICCRESPONSE
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
-	RILUICCRESPONSE
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCRESPONSE, RILUICCRESPONSE"
req.product: Windows 10 or later.
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




### -field cbSize


### -field dwParams


### -field dwStatusWord1


### -field dwStatusWord2


### -field dwResponseSize


### -field pbResponse

