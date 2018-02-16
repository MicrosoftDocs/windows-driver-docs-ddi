---
UID: NE:rilapitypes.RILMSGMWIPRIORITY
title: RILMSGMWIPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwipriority_2.htm
old-project: netvista
ms.assetid: a9efeb68-8838-476f-8ffb-11c8c71163fc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGMWIPRIORITY_MAX, RILMSGMWIPRIORITY, RIL_MSGMWIPRIORITY_URGENT, RILMSGMWIPRIORITY enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGMWIPRIORITY_LOW, rilapitypes/RIL_MSGMWIPRIORITY_NORMAL, RIL_MSGMWIPRIORITY_LOW, rilapitypes/RIL_MSGMWIPRIORITY_MAX, rilapitypes/RIL_MSGMWIPRIORITY_EMERGENCY, rilapitypes/RIL_MSGMWIPRIORITY_URGENT, RIL_MSGMWIPRIORITY_NORMAL, netvista.rilmsgmwipriority_2, RIL_MSGMWIPRIORITY_EMERGENCY, rilapitypes/RILMSGMWIPRIORITY
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
-	RILMSGMWIPRIORITY
product: Windows
targetos: Windows
req.typenames: RILMSGMWIPRIORITY
req.product: Windows 10 or later.
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

