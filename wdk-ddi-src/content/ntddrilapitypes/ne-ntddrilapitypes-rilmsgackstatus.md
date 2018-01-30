---
UID: NE:ntddrilapitypes.RILMSGACKSTATUS
title: RILMSGACKSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgackstatus.htm
old-project: netvista
ms.assetid: 551193d0-596c-40bf-9a31-f8b6eb330e25
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_MSGACKSTATUS_MAX, ntddrilapitypes/RIL_MSGACKSTATUS_FAIL_MEM_FULL, RIL_MSGACKSTATUS_FAIL_MEM_FULL, RILMSGACKSTATUS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_MSGACKSTATUS_ERROR, ntddrilapitypes/RILMSGACKSTATUS, RIL_MSGACKSTATUS_MAX, RILMSGACKSTATUS, RIL_MSGACKSTATUS_ERROR, netvista.rilmsgackstatus
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
-	RILMSGACKSTATUS
product: Windows
targetos: Windows
req.typenames: RILMSGACKSTATUS
---

# RILMSGACKSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGACKSTATUS { 
  RIL_MSGACKSTATUS_FAIL_MEM_FULL,
  RIL_MSGACKSTATUS_ERROR,
  RIL_MSGACKSTATUS_MAX
} RILMSGACKSTATUS;
````


## -enum-fields




### -field RIL_MSGACKSTATUS_STORED



### -field RIL_MSGACKSTATUS_FAIL_MEM_FULL



### -field RIL_MSGACKSTATUS_ERROR



### -field RIL_MSGACKSTATUS_MAX


