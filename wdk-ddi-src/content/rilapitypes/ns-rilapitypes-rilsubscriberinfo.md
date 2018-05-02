---
UID: NS:rilapitypes.RILSUBSCRIBERINFO
title: RILSUBSCRIBERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubscriberinfo_2.htm
old-project: netvista
ms.assetid: 4afb3184-0534-43b1-9b88-4aac04d26c4a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILSUBSCRIBERINFO, RILSUBSCRIBERINFO, RILSUBSCRIBERINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsubscriberinfo_2, rilapitypes/RILSUBSCRIBERINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSUBSCRIBERINFO
product:
- Windows
targetos: Windows
req.typenames: RILSUBSCRIBERINFO, *LPRILSUBSCRIBERINFO
req.product: Windows 10 or later.
---

# RILSUBSCRIBERINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSUBSCRIBERINFO {
  DWORD                         cbSize;
  DWORD                         dwParams;
  RILADDRESS                    raAddress;
  WCHAR [MAXLENGTH_DESCRIPTION] wszDescription;
  RILSUBSCRIBERINFOSERVICE      dwService;
} RILSUBSCRIBERINFO, RILSUBSCRIBERINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field raAddress


### -field wszDescription


### -field dwService

