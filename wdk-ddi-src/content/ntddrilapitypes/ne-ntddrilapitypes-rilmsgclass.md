---
UID: NE:ntddrilapitypes.RILMSGCLASS
title: RILMSGCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgclass.htm
old-project: netvista
ms.assetid: 2f7e2c4f-56bc-4efd-8911-5161b657dbea
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGCLASS, RILMSGCLASS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGCLASS_ALL, RIL_MSGCLASS_BROADCAST, RIL_MSGCLASS_INCOMING, RIL_MSGCLASS_OUTGOING, netvista.rilmsgclass, ntddrilapitypes/RILMSGCLASS, ntddrilapitypes/RIL_MSGCLASS_ALL, ntddrilapitypes/RIL_MSGCLASS_BROADCAST, ntddrilapitypes/RIL_MSGCLASS_INCOMING, ntddrilapitypes/RIL_MSGCLASS_OUTGOING
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILMSGCLASS
product: Windows
targetos: Windows
req.typenames: RILMSGCLASS
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

