---
UID: NE:ntddrilapitypes.RILSMSREADYSTATE
title: RILSMSREADYSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystate.htm
old-project: netvista
ms.assetid: f37b1e31-d0fa-4b0a-bab6-131b3bf1bdcd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SMSREADYSTATE_ALL, RILSMSREADYSTATE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_SMSREADYSTATE_ALL, RIL_SMSREADY_UICCREADY, ntddrilapitypes/RILSMSREADYSTATE, ntddrilapitypes/RIL_SMSREADY_SERVICEREADY_3GPP2, netvista.rilsmsreadystate, ntddrilapitypes/RIL_SMSREADY_UICCREADY, RIL_SMSREADY_SERVICEREADY_3GPP2, RILSMSREADYSTATE
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
-	RILSMSREADYSTATE
product: Windows
targetos: Windows
req.typenames: RILSMSREADYSTATE
---

# RILSMSREADYSTATE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILSMSREADYSTATE { 
  RIL_SMSREADY_SERVICEREADY_3GPP2,
  RIL_SMSREADY_UICCREADY,
  RIL_SMSREADYSTATE_ALL
} RILSMSREADYSTATE;
````


## -enum-fields




### -field RIL_SMSREADY_SERVICEREADY_3GPP


### -field RIL_SMSREADY_SERVICEREADY_3GPP2


### -field RIL_SMSREADY_UICCREADY


### -field RIL_SMSREADYSTATE_ALL

