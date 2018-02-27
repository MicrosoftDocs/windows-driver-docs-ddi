---
UID: NE:ntddrilapitypes.RILMSGCDMAMSGSTATUSTYPE
title: RILMSGCDMAMSGSTATUSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgstatustype.htm
old-project: netvista
ms.assetid: 60365fd7-3897-4948-a251-098e5a91c959
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGCDMAMSGSTATUSTYPE, RILMSGCDMAMSGSTATUSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_MSGSTATUSTYPE_DELIVERYACK, RIL_MSGSTATUSTYPE_MAX, RIL_MSGSTATUSTYPE_READACK, RIL_MSGSTATUSTYPE_USERACK, netvista.rilmsgcdmamsgstatustype, ntddrilapitypes/RILMSGCDMAMSGSTATUSTYPE, ntddrilapitypes/RIL_MSGSTATUSTYPE_DELIVERYACK, ntddrilapitypes/RIL_MSGSTATUSTYPE_MAX, ntddrilapitypes/RIL_MSGSTATUSTYPE_READACK, ntddrilapitypes/RIL_MSGSTATUSTYPE_USERACK
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
-	RILMSGCDMAMSGSTATUSTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGSTATUSTYPE
---

# RILMSGCDMAMSGSTATUSTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGCDMAMSGSTATUSTYPE { 
  RIL_MSGSTATUSTYPE_DELIVERYACK,
  RIL_MSGSTATUSTYPE_USERACK,
  RIL_MSGSTATUSTYPE_READACK,
  RIL_MSGSTATUSTYPE_MAX
} RILMSGCDMAMSGSTATUSTYPE;
````


## -enum-fields




### -field RIL_MSGSTATUSTYPE_BEARERACK


### -field RIL_MSGSTATUSTYPE_DELIVERYACK


### -field RIL_MSGSTATUSTYPE_USERACK


### -field RIL_MSGSTATUSTYPE_READACK


### -field RIL_MSGSTATUSTYPE_MAX

