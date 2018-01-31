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
ms.keywords: RIL_MSGSTATUS_RECUNREAD, RIL_MSGSTATUS_RECREAD, ntddrilapitypes/RIL_MSGSTATUS_STOUNSENT, ntddrilapitypes/RIL_MSGSTATUS_RECUNREAD, ntddrilapitypes/RIL_MSGSTATUS_STOSENT, ntddrilapitypes/RIL_MSGSTATUS_MAX, netvista.rilmessagestatus, RIL_MSGSTATUS_STOSENT, RIL_MSGSTATUS_MAX, RILMESSAGESTATUS, RILMESSAGESTATUS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILMESSAGESTATUS, RIL_MSGSTATUS_STOUNSENT, ntddrilapitypes/RIL_MSGSTATUS_RECREAD
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



#### - RIL_MSGSTATUS_RECUNREAD



#### - RIL_MSGSTATUS_RECREAD



#### - RIL_MSGSTATUS_STOUNSENT



#### - RIL_MSGSTATUS_STOSENT



#### - RIL_MSGSTATUS_MAX


