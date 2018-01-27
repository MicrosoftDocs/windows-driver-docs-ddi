---
UID: NS:rilapitypes.RILUNBLOCKUICCLOCKPARAMS
title: RILUNBLOCKUICCLOCKPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunblockuicclockparams_2.htm
old-project: netvista
ms.assetid: 7b5245e9-7f25-4697-932a-d7d1416e921c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUNBLOCKUICCLOCKPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILUNBLOCKUICCLOCKPARAMS, *LPRILUNBLOCKUICCLOCKPARAMS, RILUNBLOCKUICCLOCKPARAMS, netvista.rilunblockuicclockparams_2
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
-	RILUNBLOCKUICCLOCKPARAMS
product: Windows
targetos: Windows
req.typenames: RILUNBLOCKUICCLOCKPARAMS, *LPRILUNBLOCKUICCLOCKPARAMS
req.product: Windows 10 or later.
---

# RILUNBLOCKUICCLOCKPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUNBLOCKUICCLOCKPARAMS {
  RILUICCLOCKCREDENTIAL     lockCredential;
  char [MAXLENGTH_PASSWORD] szNewPassword;
} RILUNBLOCKUICCLOCKPARAMS, RILUNBLOCKUICCLOCKPARAMS;
````


## -struct-fields




### -field lockCredential



### -field szNewPassword


