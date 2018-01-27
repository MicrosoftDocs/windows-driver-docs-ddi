---
UID: NS:rilapitypes.RILCALLMEDIAOFFERANSWER
title: RILCALLMEDIAOFFERANSWER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswer_2.htm
old-project: netvista
ms.assetid: 1ba861f5-b790-4e5a-88fa-49e05239219c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediaofferanswer_2, *LPRILCALLMEDIAOFFERANSWER
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
-	RILCALLMEDIAOFFERANSWER
product: Windows
targetos: Windows
req.typenames: *LPRILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERANSWER structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLMEDIAOFFERANSWER {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILCALLMEDIAID           stID;
  BOOL                     fChange;
  RILCALLMEDIAOFFERACTION  dwMediaAction;
  RILCALLMEDIASTATE        stOldState;
  RILCALLMEDIASTATE        stNewState;
} RILCALLMEDIAOFFERANSWER, RILCALLMEDIAOFFERANSWER;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field stID



### -field fChange



### -field dwMediaAction



### -field stOldState



### -field stNewState


