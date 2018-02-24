---
UID: NE:rilapitypes.RILMSGCLASS
title: RILMSGCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgclass_2.htm
old-project: netvista
ms.assetid: 95818f9a-9053-4fb3-8bcb-6e318ed6bae5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RIL_MSGCLASS_INCOMING, RILMSGCLASS, rilapitypes/RIL_MSGCLASS_OUTGOING, RILMSGCLASS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGCLASS_INCOMING, netvista.rilmsgclass_2, rilapitypes/RIL_MSGCLASS_BROADCAST, rilapitypes/RIL_MSGCLASS_ALL, RIL_MSGCLASS_OUTGOING, rilapitypes/RILMSGCLASS, RIL_MSGCLASS_ALL, RIL_MSGCLASS_BROADCAST
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
-	RILMSGCLASS
product: Windows
targetos: Windows
req.typenames: RILMSGCLASS
req.product: Windows 10 or later.
---

# RILMSGCLASS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGCLASS { 
  RIL_MSGCLASS_INCOMING,
  RIL_MSGCLASS_OUTGOING,
  RIL_MSGCLASS_BROADCAST,
  RIL_MSGCLASS_ALL
} RILMSGCLASS;
````


## -enum-fields




### -field RIL_MSGCLASS_NONE


### -field RIL_MSGCLASS_INCOMING


### -field RIL_MSGCLASS_OUTGOING


### -field RIL_MSGCLASS_BROADCAST


### -field RIL_MSGCLASS_ALL

