---
UID: NE:rilapitypes.RILMESSAGESTATUS
title: RILMESSAGESTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagestatus_2.htm
old-project: netvista
ms.assetid: 30ae1eff-447c-4f6f-8f6c-cd8bc657d32d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, E, G, I, L, M, R, RILMESSAGESTATUS, RILMESSAGESTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGSTATUS_MAX, RIL_MSGSTATUS_RECREAD, RIL_MSGSTATUS_RECUNREAD, RIL_MSGSTATUS_STOSENT, RIL_MSGSTATUS_STOUNSENT, S, T, U, netvista.rilmessagestatus_2, rilapitypes/RILMESSAGESTATUS, rilapitypes/RIL_MSGSTATUS_MAX, rilapitypes/RIL_MSGSTATUS_RECREAD, rilapitypes/RIL_MSGSTATUS_RECUNREAD, rilapitypes/RIL_MSGSTATUS_STOSENT, rilapitypes/RIL_MSGSTATUS_STOUNSENT"
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
-	RILMESSAGESTATUS
product: Windows
targetos: Windows
req.typenames: RILMESSAGESTATUS
req.product: Windows 10 or later.
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

