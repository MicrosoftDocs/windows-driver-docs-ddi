---
UID: NS:ntddrilapitypes.RILMANAGECALLSPARAMS_V4
title: RILMANAGECALLSPARAMS_V4
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v4.htm
old-project: netvista
ms.assetid: 8e38c6d5-bd61-455e-a628-b4e6ef9c936c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *LPRILMANAGECALLSPARAMS_V4, *LPRILMANAGECALLSPARAMS, ntddrilapitypes/RILMANAGECALLSPARAMS_V4, netvista.rilmanagecallsparams_v4, RILMANAGECALLSPARAMS_V4, RILMANAGECALLSPARAMS, RILMANAGECALLSPARAMS_V4 structure [Network Drivers Starting with Windows Vista]
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
-	RILMANAGECALLSPARAMS_V4
product: Windows
targetos: Windows
req.typenames: RILMANAGECALLSPARAMS, *LPRILMANAGECALLSPARAMS_V4, RILMANAGECALLSPARAMS_V4, *LPRILMANAGECALLSPARAMS
---

# RILMANAGECALLSPARAMS_V4 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILMANAGECALLSPARAMS_V4 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
  BOOL                        fHasOfferAnswer;
  RILCALLMEDIAOFFERANSWERSET  rcmOfferAnswer;
  RILADDRESS                  raAddress;
  RILCALLRTTACTION            dwRTTAction;
} RILMANAGECALLSPARAMS_V4, RILMANAGECALLSPARAMS_V4;
````


## -struct-fields




### -field dwExecutor



### -field dwCommand



### -field dwID



### -field fHasOfferAnswer



### -field rcmOfferAnswer



### -field raAddress



### -field dwRTTAction


