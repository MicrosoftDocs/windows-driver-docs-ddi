---
UID: NS:rilapitypes.RILSETCALLBARRINGSTATUSPARAMS
title: RILSETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallbarringstatusparams_2.htm
old-project: netvista
ms.assetid: 6116e564-93e6-45ba-8759-aab7d82783b2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetcallbarringstatusparams_2, rilapitypes/RILSETCALLBARRINGSTATUSPARAMS"
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
-	RILSETCALLBARRINGSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETCALLBARRINGSTATUSPARAMS, *LPRILSETCALLBARRINGSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILSETCALLBARRINGSTATUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSETCALLBARRINGSTATUSPARAMS {
  DWORD                             dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE    dwType;
  BOOL                              fAllClasses;
  DWORD                             dwInfoClasses;
  BOOL                              fPassword;
  char [MAXLENGTH_PASSWORD]         szPassword;
  RILCALLBARRINGSTATUSPARAMSSTATUS  dwStatus;
} RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwType


### -field fAllClasses


### -field dwInfoClasses


### -field fPassword


### -field szPassword


### -field dwStatus

