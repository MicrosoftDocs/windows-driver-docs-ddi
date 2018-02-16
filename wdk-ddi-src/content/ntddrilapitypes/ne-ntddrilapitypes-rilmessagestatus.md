---
UID: NE:ntddrilapitypes.RILMESSAGESTATUS
title: RILMESSAGESTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagestatus.htm
old-project: netvista
ms.assetid: 8c111231-f94b-4e52-9887-59d07fe70937
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_MSGSTATUS_STOUNSENT, RIL_MSGSTATUS_MAX, RIL_MSGSTATUS_RECREAD, RIL_MSGSTATUS_STOSENT, ntddrilapitypes/RIL_MSGSTATUS_RECUNREAD, ntddrilapitypes/RILMESSAGESTATUS, RILMESSAGESTATUS, ntddrilapitypes/RIL_MSGSTATUS_STOSENT, netvista.rilmessagestatus, ntddrilapitypes/RIL_MSGSTATUS_MAX, RIL_MSGSTATUS_RECUNREAD, ntddrilapitypes/RIL_MSGSTATUS_RECREAD, RILMESSAGESTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGSTATUS_STOUNSENT
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
-	RILMESSAGESTATUS
product: Windows
targetos: Windows
req.typenames: RILMESSAGESTATUS
---

# RILMESSAGESTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMESSAGESTATUS { 
  RIL_MSGSTATUS_RECUNREAD,
  RIL_MSGSTATUS_RECREAD,
  RIL_MSGSTATUS_STOUNSENT,
  RIL_MSGSTATUS_STOSENT,
  RIL_MSGSTATUS_MAX
} RILMESSAGESTATUS;
````


## -enum-fields




### -field RIL_MSGSTATUS_UNKNOWN


### -field RIL_MSGSTATUS_RECUNREAD


### -field RIL_MSGSTATUS_RECREAD


### -field RIL_MSGSTATUS_STOUNSENT


### -field RIL_MSGSTATUS_STOSENT


### -field RIL_MSGSTATUS_MAX

