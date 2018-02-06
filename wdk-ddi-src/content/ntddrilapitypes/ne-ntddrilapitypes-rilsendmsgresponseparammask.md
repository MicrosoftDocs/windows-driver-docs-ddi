---
UID: NE:ntddrilapitypes.RILSENDMSGRESPONSEPARAMMASK
title: RILSENDMSGRESPONSEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgresponseparammask.htm
old-project: netvista
ms.assetid: d3bf2b1a-22ac-4b37-a442-ecd8a2108b46
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_MSGRES_GWLRELAYCODE, netvista.rilsendmsgresponseparammask, ntddrilapitypes/RIL_PARAM_MSGRES_MSGID, RIL_PARAM_MSGRES_CDMAERRORCLASS, RIL_PARAM_MSGRES_GWLRELAYCODE, ntddrilapitypes/RILSENDMSGRESPONSEPARAMMASK, ntddrilapitypes/RIL_PARAM_MSGRES_CDMACAUSECODE, RILSENDMSGRESPONSEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_MSGRES_GWLTRANSPORTCODE, RIL_PARAM_MSGRES_ALL, RILSENDMSGRESPONSEPARAMMASK, RIL_PARAM_MSGRES_GWLTRANSPORTCODE, ntddrilapitypes/RIL_PARAM_MSGRES_ALL, RIL_PARAM_MSGRES_CDMACAUSECODE, RIL_PARAM_MSGRES_MSGID, ntddrilapitypes/RIL_PARAM_MSGRES_CDMAERRORCLASS
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
-	RILSENDMSGRESPONSEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSENDMSGRESPONSEPARAMMASK
---

# RILSENDMSGRESPONSEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILSENDMSGRESPONSEPARAMMASK { 
  RIL_PARAM_MSGRES_CDMACAUSECODE,
  RIL_PARAM_MSGRES_CDMAERRORCLASS,
  RIL_PARAM_MSGRES_GWLTRANSPORTCODE,
  RIL_PARAM_MSGRES_GWLRELAYCODE,
  RIL_PARAM_MSGRES_MSGID,
  RIL_PARAM_MSGRES_ALL
} RILSENDMSGRESPONSEPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_MSGRES_RETURN



### -field RIL_PARAM_MSGRES_CDMACAUSECODE



### -field RIL_PARAM_MSGRES_CDMAERRORCLASS



### -field RIL_PARAM_MSGRES_GWLTRANSPORTCODE



### -field RIL_PARAM_MSGRES_GWLRELAYCODE



### -field RIL_PARAM_MSGRES_MSGID



### -field RIL_PARAM_MSGRES_ALL


