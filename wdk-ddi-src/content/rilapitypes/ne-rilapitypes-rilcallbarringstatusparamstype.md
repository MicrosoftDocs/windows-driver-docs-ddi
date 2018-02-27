---
UID: NE:rilapitypes.RILCALLBARRINGSTATUSPARAMSTYPE
title: RILCALLBARRINGSTATUSPARAMSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallbarringstatusparamstype_2.htm
old-project: netvista
ms.assetid: ed54bc8d-0cf2-4d6a-935c-b5b2a539eea0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLBARRINGSTATUSPARAMSTYPE, RILCALLBARRINGSTATUSPARAMSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_BARRTYPE_ALL, RIL_BARRTYPE_ALLBARRING, RIL_BARRTYPE_ALLINCOMING, RIL_BARRTYPE_ALLINCOMINGBARRING, RIL_BARRTYPE_ALLOUTGOINGBARRING, RIL_BARRTYPE_INCOMINGNOTINUICC, RIL_BARRTYPE_INCOMINGROAMING, RIL_BARRTYPE_OUTGOINGINT, RIL_BARRTYPE_OUTGOINGINTEXTOHOME, netvista.rilcallbarringstatusparamstype_2, rilapitypes/RILCALLBARRINGSTATUSPARAMSTYPE, rilapitypes/RIL_BARRTYPE_ALL, rilapitypes/RIL_BARRTYPE_ALLBARRING, rilapitypes/RIL_BARRTYPE_ALLINCOMING, rilapitypes/RIL_BARRTYPE_ALLINCOMINGBARRING, rilapitypes/RIL_BARRTYPE_ALLOUTGOINGBARRING, rilapitypes/RIL_BARRTYPE_INCOMINGNOTINUICC, rilapitypes/RIL_BARRTYPE_INCOMINGROAMING, rilapitypes/RIL_BARRTYPE_OUTGOINGINT, rilapitypes/RIL_BARRTYPE_OUTGOINGINTEXTOHOME
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
-	RILCALLBARRINGSTATUSPARAMSTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLBARRINGSTATUSPARAMSTYPE
req.product: Windows 10 or later.
---

# RILCALLBARRINGSTATUSPARAMSTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLBARRINGSTATUSPARAMSTYPE { 
  RIL_BARRTYPE_OUTGOINGINT,
  RIL_BARRTYPE_OUTGOINGINTEXTOHOME,
  RIL_BARRTYPE_ALLINCOMING,
  RIL_BARRTYPE_INCOMINGROAMING,
  RIL_BARRTYPE_INCOMINGNOTINUICC,
  RIL_BARRTYPE_ALLBARRING,
  RIL_BARRTYPE_ALLOUTGOINGBARRING,
  RIL_BARRTYPE_ALLINCOMINGBARRING,
  RIL_BARRTYPE_ALL
} RILCALLBARRINGSTATUSPARAMSTYPE;
````


## -enum-fields




### -field RIL_BARRTYPE_ALLOUTGOING


### -field RIL_BARRTYPE_OUTGOINGINT


### -field RIL_BARRTYPE_OUTGOINGINTEXTOHOME


### -field RIL_BARRTYPE_ALLINCOMING


### -field RIL_BARRTYPE_INCOMINGROAMING


### -field RIL_BARRTYPE_INCOMINGNOTINUICC


### -field RIL_BARRTYPE_ALLBARRING


### -field RIL_BARRTYPE_ALLOUTGOINGBARRING


### -field RIL_BARRTYPE_ALLINCOMINGBARRING


### -field RIL_BARRTYPE_ALL

