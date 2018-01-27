---
UID: NS:rilapitypes.RILSENDRTTDATAPARAMS
title: RILSENDRTTDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrttdataparams_2.htm
old-project: netvista
ms.assetid: 9fc4662f-e827-473a-8e18-f60afb62cd5e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsendrttdataparams_2, RILSENDRTTDATAPARAMS structure [Network Drivers Starting with Windows Vista], RILSENDRTTDATAPARAMS, rilapitypes/RILSENDRTTDATAPARAMS, *LPRILSENDRTTDATAPARAMS
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
-	RILSENDRTTDATAPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDRTTDATAPARAMS, *LPRILSENDRTTDATAPARAMS
req.product: Windows 10 or later.
---

# RILSENDRTTDATAPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSENDRTTDATAPARAMS {
  DWORD                     cbSize;
  DWORD                     dwID;
  DWORD                     dwExecutor;
  WCHAR [MAXLENGTH_RTTDATA] wszRTTText;
} RILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS;
````


## -struct-fields




### -field cbSize



### -field dwID



### -field dwExecutor



### -field wszRTTText


