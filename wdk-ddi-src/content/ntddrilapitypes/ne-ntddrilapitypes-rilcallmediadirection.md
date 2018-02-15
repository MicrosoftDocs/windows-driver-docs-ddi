---
UID: NE:ntddrilapitypes.RILCALLMEDIADIRECTION
title: RILCALLMEDIADIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediadirection.htm
old-project: netvista
ms.assetid: 8c6b2329-9956-43c1-8a4d-ef9587cf0980
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIADIRECTION, netvista.rilcallmediadirection, RIL_CALLMEDIADIRECTION_RXTX, ntddrilapitypes/RIL_CALLMEDIADIRECTION_RXTX, ntddrilapitypes/RIL_CALLMEDIADIRECTION_MAX, RIL_CALLMEDIADIRECTION_TX, ntddrilapitypes/RILCALLMEDIADIRECTION, ntddrilapitypes/RIL_CALLMEDIADIRECTION_RX, RIL_CALLMEDIADIRECTION_MAX, RILCALLMEDIADIRECTION enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALLMEDIADIRECTION_TX, RIL_CALLMEDIADIRECTION_RX
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
-	RILCALLMEDIADIRECTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIADIRECTION
---

# RILCALLMEDIADIRECTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLMEDIADIRECTION { 
  RIL_CALLMEDIADIRECTION_RX,
  RIL_CALLMEDIADIRECTION_TX,
  RIL_CALLMEDIADIRECTION_RXTX,
  RIL_CALLMEDIADIRECTION_MAX
} RILCALLMEDIADIRECTION;
````


## -enum-fields




### -field RIL_CALLMEDIADIRECTION_NONE


### -field RIL_CALLMEDIADIRECTION_RX


### -field RIL_CALLMEDIADIRECTION_TX


### -field RIL_CALLMEDIADIRECTION_RXTX


### -field RIL_CALLMEDIADIRECTION_MAX

