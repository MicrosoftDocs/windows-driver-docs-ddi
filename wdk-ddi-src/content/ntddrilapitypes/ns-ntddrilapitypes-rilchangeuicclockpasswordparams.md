---
UID: NS:ntddrilapitypes.RILCHANGEUICCLOCKPASSWORDPARAMS
title: RILCHANGEUICCLOCKPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangeuicclockpasswordparams.htm
old-project: netvista
ms.assetid: 00e2fe6f-fd8b-45d1-9fd2-d90c515c3571
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilchangeuicclockpasswordparams, ntddrilapitypes/RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS structure [Network Drivers Starting with Windows Vista], RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS
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
-	RILCHANGEUICCLOCKPASSWORDPARAMS
product: Windows
targetos: Windows
req.typenames: RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS
---

# RILCHANGEUICCLOCKPASSWORDPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCHANGEUICCLOCKPASSWORDPARAMS {
  RILUICCLOCKCREDENTIAL  lockCredential;
  char [256]             szNewPassword;
} RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS;
````


## -struct-fields




### -field lockCredential



### -field szNewPassword


