---
UID: NE:ntddrilapitypes.RILMSGMWIPRIORITY
title: RILMSGMWIPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwipriority.htm
old-project: netvista
ms.assetid: a974af39-a4a6-44f2-9010-e612f50c83df
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, G, I, L, M, O, P, R, RILMSGMWIPRIORITY, RILMSGMWIPRIORITY enumeration [Network Drivers Starting with Windows Vista], RIL_MSGMWIPRIORITY_EMERGENCY, RIL_MSGMWIPRIORITY_LOW, RIL_MSGMWIPRIORITY_MAX, RIL_MSGMWIPRIORITY_NORMAL, RIL_MSGMWIPRIORITY_URGENT, S, T, W, Y, netvista.rilmsgmwipriority, ntddrilapitypes/RILMSGMWIPRIORITY, ntddrilapitypes/RIL_MSGMWIPRIORITY_EMERGENCY, ntddrilapitypes/RIL_MSGMWIPRIORITY_LOW, ntddrilapitypes/RIL_MSGMWIPRIORITY_MAX, ntddrilapitypes/RIL_MSGMWIPRIORITY_NORMAL, ntddrilapitypes/RIL_MSGMWIPRIORITY_URGENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILMSGMWIPRIORITY
product: Windows
targetos: Windows
req.typenames: RILMSGMWIPRIORITY
---

# RILMSGMWIPRIORITY enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGMWIPRIORITY { 
  RIL_MSGMWIPRIORITY_LOW,
  RIL_MSGMWIPRIORITY_NORMAL,
  RIL_MSGMWIPRIORITY_URGENT,
  RIL_MSGMWIPRIORITY_EMERGENCY,
  RIL_MSGMWIPRIORITY_MAX
} RILMSGMWIPRIORITY;
````


## -enum-fields




### -field RIL_MSGMWIPRIORITY_UNKNOWN


### -field RIL_MSGMWIPRIORITY_LOW


### -field RIL_MSGMWIPRIORITY_NORMAL


### -field RIL_MSGMWIPRIORITY_URGENT


### -field RIL_MSGMWIPRIORITY_EMERGENCY


### -field RIL_MSGMWIPRIORITY_MAX

