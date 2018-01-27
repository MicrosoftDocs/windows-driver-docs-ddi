---
UID: NS:ntddrilapitypes.RILMANAGECALLSPARAMS_V2
title: RILMANAGECALLSPARAMS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v2.htm
old-project: netvista
ms.assetid: 7a4e0930-b499-4abd-bbf6-326ae928b5c5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILMANAGECALLSPARAMS_V2, netvista.rilmanagecallsparams_v2, RILMANAGECALLSPARAMS_V2 structure [Network Drivers Starting with Windows Vista], *LPRILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2
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
-	RILMANAGECALLSPARAMS_V2
product: Windows
targetos: Windows
req.typenames: *LPRILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2
---

# RILMANAGECALLSPARAMS_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMANAGECALLSPARAMS_V2 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
  BOOL                        fHasOfferAnswer;
  RILCALLMEDIAOFFERANSWERSET  rcmOfferAnswer;
} RILMANAGECALLSPARAMS_V2, RILMANAGECALLSPARAMS_V2;
````


## -struct-fields




### -field dwExecutor



### -field dwCommand



### -field dwID



### -field fHasOfferAnswer



### -field rcmOfferAnswer


