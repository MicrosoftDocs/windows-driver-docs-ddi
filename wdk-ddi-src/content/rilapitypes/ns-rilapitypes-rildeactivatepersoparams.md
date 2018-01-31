---
UID: NS:rilapitypes.RILDEACTIVATEPERSOPARAMS
title: RILDEACTIVATEPERSOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeactivatepersoparams_2.htm
old-project: netvista
ms.assetid: 525c0861-3537-4175-8415-7db13686dd7a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILDEACTIVATEPERSOPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILDEACTIVATEPERSOPARAMS, netvista.rildeactivatepersoparams_2, *LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS
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
-	RILDEACTIVATEPERSOPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS"
req.product: Windows 10 or later.
---

# RILDEACTIVATEPERSOPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILDEACTIVATEPERSOPARAMS {
  DWORD                     dwPersoFeature;
  char [MAXLENGTH_PASSWORD] szPassword;
} RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS;
````


## -struct-fields




#### - dwPersoFeature



#### - szPassword


