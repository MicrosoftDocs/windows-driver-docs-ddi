---
UID: NS:rilapitypes.RILRADIOSTATEPASSWORD
title: RILRADIOSTATEPASSWORD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostatepassword_2.htm
old-project: netvista
ms.assetid: 879f38f7-ae13-4a39-bc68-b5c5f5f4f32c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD structure [Network Drivers Starting with Windows Vista], netvista.rilradiostatepassword_2, *LPRILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD
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
-	RILRADIOSTATEPASSWORD
product: Windows
targetos: Windows
req.typenames: "*LPRILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD"
req.product: Windows 10 or later.
---

# RILRADIOSTATEPASSWORD structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRADIOSTATEPASSWORD {
  DWORD                                 dwPasswordId;
  WCHAR [MAXLENGTH_RADIOPASSWORD_WCHAR] wszPassword;
} RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD;
````


## -struct-fields




#### - dwPasswordId



#### - wszPassword


