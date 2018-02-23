---
UID: NE:ntddrilapitypes.RILMSGDCSTYPE
title: RILMSGDCSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcstype.htm
old-project: netvista
ms.assetid: 557fc92e-6550-44ea-ac09-bb0b74e1275f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_DCSTYPE_LANGUAGE, ntddrilapitypes/RIL_DCSTYPE_LANGUAGE, ntddrilapitypes/RILMSGDCSTYPE, RIL_DCSTYPE_MSGCLASS, RILMSGDCSTYPE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_DCSTYPE_MSGWAIT, RIL_DCSTYPE_MAX, ntddrilapitypes/RIL_DCSTYPE_MSGCLASS, ntddrilapitypes/RIL_DCSTYPE_MAX, RIL_DCSTYPE_MSGWAIT, RILMSGDCSTYPE, netvista.rilmsgdcstype
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
-	RILMSGDCSTYPE
product: Windows
targetos: Windows
req.typenames: RILMSGDCSTYPE
---

# RILMSGDCSTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGDCSTYPE { 
  RIL_DCSTYPE_MSGWAIT,
  RIL_DCSTYPE_MSGCLASS,
  RIL_DCSTYPE_LANGUAGE,
  RIL_DCSTYPE_MAX
} RILMSGDCSTYPE;
````


## -enum-fields




### -field RIL_DCSTYPE_GENERAL


### -field RIL_DCSTYPE_MSGWAIT


### -field RIL_DCSTYPE_MSGCLASS


### -field RIL_DCSTYPE_LANGUAGE


### -field RIL_DCSTYPE_MAX

