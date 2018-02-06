---
UID: NE:rilapitypes.RILCALLMEDIAOFFERANSWERTYPE
title: RILCALLMEDIAOFFERANSWERTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferanswertype_2.htm
old-project: netvista
ms.assetid: 098392dc-f966-44f8-9202-9663b8cabc7e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIAOFFERANSWERTYPE, RIL_CALLMEDIAOFFERANSWERTYPE_MAX, rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_PEER_OFFER, RIL_CALLMEDIAOFFERANSWERTYPE_PEER_ANSWER, RIL_CALLMEDIAOFFERANSWERTYPE_PEER_OFFER, rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_CURRENT, RIL_CALLMEDIAOFFERANSWERTYPE_ANSWER, RILCALLMEDIAOFFERANSWERTYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_OFFER, rilapitypes/RILCALLMEDIAOFFERANSWERTYPE, RIL_CALLMEDIAOFFERANSWERTYPE_OFFER, RIL_CALLMEDIAOFFERANSWERTYPE_CURRENT, rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_PEER_ANSWER, netvista.rilcallmediaofferanswertype_2, rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_MAX, rilapitypes/RIL_CALLMEDIAOFFERANSWERTYPE_ANSWER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILCALLMEDIAOFFERANSWERTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERANSWERTYPE
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERANSWERTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLMEDIAOFFERANSWERTYPE { 
  RIL_CALLMEDIAOFFERANSWERTYPE_CURRENT,
  RIL_CALLMEDIAOFFERANSWERTYPE_OFFER,
  RIL_CALLMEDIAOFFERANSWERTYPE_ANSWER,
  RIL_CALLMEDIAOFFERANSWERTYPE_PEER_OFFER,
  RIL_CALLMEDIAOFFERANSWERTYPE_PEER_ANSWER,
  RIL_CALLMEDIAOFFERANSWERTYPE_MAX
} RILCALLMEDIAOFFERANSWERTYPE;
````


## -enum-fields




### -field RIL_CALLMEDIAOFFERANSWERTYPE_UNKNOWN



### -field RIL_CALLMEDIAOFFERANSWERTYPE_CURRENT



### -field RIL_CALLMEDIAOFFERANSWERTYPE_OFFER



### -field RIL_CALLMEDIAOFFERANSWERTYPE_ANSWER



### -field RIL_CALLMEDIAOFFERANSWERTYPE_PEER_OFFER



### -field RIL_CALLMEDIAOFFERANSWERTYPE_PEER_ANSWER



### -field RIL_CALLMEDIAOFFERANSWERTYPE_MAX


