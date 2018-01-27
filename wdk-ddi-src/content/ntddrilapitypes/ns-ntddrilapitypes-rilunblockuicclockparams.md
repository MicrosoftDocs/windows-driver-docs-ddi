---
UID: NS:ntddrilapitypes.RILUNBLOCKUICCLOCKPARAMS
title: RILUNBLOCKUICCLOCKPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunblockuicclockparams.htm
old-project: netvista
ms.assetid: 48d1deeb-8862-4e01-aa22-119a53aa4aba
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUNBLOCKUICCLOCKPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILUNBLOCKUICCLOCKPARAMS, *LPRILUNBLOCKUICCLOCKPARAMS, RILUNBLOCKUICCLOCKPARAMS, netvista.rilunblockuicclockparams
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
-	RILUNBLOCKUICCLOCKPARAMS
product: Windows
targetos: Windows
req.typenames: RILUNBLOCKUICCLOCKPARAMS, *LPRILUNBLOCKUICCLOCKPARAMS
---

# RILUNBLOCKUICCLOCKPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUNBLOCKUICCLOCKPARAMS {
  RILUICCLOCKCREDENTIAL  lockCredential;
  char [256]             szNewPassword;
} RILUNBLOCKUICCLOCKPARAMS, RILUNBLOCKUICCLOCKPARAMS;
````


## -struct-fields




### -field lockCredential



### -field szNewPassword


