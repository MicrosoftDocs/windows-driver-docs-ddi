---
UID: NE:rilapitypes.RILCALLMEDIADIRECTION
title: RILCALLMEDIADIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediadirection_2.htm
old-project: netvista
ms.assetid: fcb5f1a4-8673-412e-95ac-5f3ca781411b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIADIRECTION, RIL_CALLMEDIADIRECTION_RXTX, RILCALLMEDIADIRECTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIADIRECTION_MAX, rilapitypes/RILCALLMEDIADIRECTION, RIL_CALLMEDIADIRECTION_RX, rilapitypes/RIL_CALLMEDIADIRECTION_MAX, rilapitypes/RIL_CALLMEDIADIRECTION_TX, netvista.rilcallmediadirection_2, rilapitypes/RIL_CALLMEDIADIRECTION_RXTX, rilapitypes/RIL_CALLMEDIADIRECTION_RX, RIL_CALLMEDIADIRECTION_TX
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
-	RILCALLMEDIADIRECTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIADIRECTION
req.product: Windows 10 or later.
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


