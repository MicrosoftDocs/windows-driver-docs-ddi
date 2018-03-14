---
UID: NS:ntddrilapitypes.RILRADIOSTATEPASSWORD
title: RILRADIOSTATEPASSWORD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostatepassword.htm
old-project: netvista
ms.assetid: 5329a688-ca72-456c-b9fa-32a922783d97
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD structure [Network Drivers Starting with Windows Vista], netvista.rilradiostatepassword, ntddrilapitypes/RILRADIOSTATEPASSWORD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILRADIOSTATEPASSWORD
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEPASSWORD, *LPRILRADIOSTATEPASSWORD
---

# RILRADIOSTATEPASSWORD structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILRADIOSTATEPASSWORD {
  DWORD      dwPasswordId;
  WCHAR [32] wszPassword;
} RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD;
````


## -struct-fields




### -field dwPasswordId


### -field wszPassword

