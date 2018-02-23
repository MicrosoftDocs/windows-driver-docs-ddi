---
UID: NE:rilapitypes.RILMSGCDMAMSGSTATUSTYPE
title: RILMSGCDMAMSGSTATUSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgstatustype_2.htm
old-project: netvista
ms.assetid: 315ca5af-103e-4c00-8dd7-10aa21bfa8a2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGCDMAMSGSTATUSTYPE, rilapitypes/RIL_MSGSTATUSTYPE_DELIVERYACK, RIL_MSGSTATUSTYPE_MAX, RILMSGCDMAMSGSTATUSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_MSGSTATUSTYPE_READACK, rilapitypes/RIL_MSGSTATUSTYPE_MAX, RIL_MSGSTATUSTYPE_USERACK, rilapitypes/RIL_MSGSTATUSTYPE_READACK, RIL_MSGSTATUSTYPE_DELIVERYACK, rilapitypes/RIL_MSGSTATUSTYPE_USERACK, netvista.rilmsgcdmamsgstatustype_2, rilapitypes/RILMSGCDMAMSGSTATUSTYPE
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
-	RILMSGCDMAMSGSTATUSTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGSTATUSTYPE
req.product: Windows 10 or later.
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

