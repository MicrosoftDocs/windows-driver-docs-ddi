---
UID: NE:rilapitypes.RILMSGCDMAMSGPRIORITY
title: RILMSGCDMAMSGPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgpriority_2.htm
old-project: netvista
ms.assetid: 3fc5f220-09ae-4f8e-8616-549a5371e2f0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGPRIORITY_URGENT, rilapitypes/RILMSGCDMAMSGPRIORITY, rilapitypes/RIL_MSGPRIORITY_EMERGENCY, RIL_MSGPRIORITY_EMERGENCY, netvista.rilmsgcdmamsgpriority_2, rilapitypes/RIL_MSGPRIORITY_MAX, RIL_MSGPRIORITY_MAX, RILMSGCDMAMSGPRIORITY, RILMSGCDMAMSGPRIORITY enumeration [Network Drivers Starting with Windows Vista], RIL_MSGPRIORITY_HIGH, rilapitypes/RIL_MSGPRIORITY_URGENT, rilapitypes/RIL_MSGPRIORITY_HIGH
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
-	RILMSGCDMAMSGPRIORITY
product: Windows
targetos: Windows
req.typenames: RILMSGCDMAMSGPRIORITY
req.product: Windows 10 or later.
---

# RILMSGCDMAMSGPRIORITY enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGCDMAMSGPRIORITY { 
  RIL_MSGPRIORITY_HIGH,
  RIL_MSGPRIORITY_URGENT,
  RIL_MSGPRIORITY_EMERGENCY,
  RIL_MSGPRIORITY_MAX
} RILMSGCDMAMSGPRIORITY;
````


## -enum-fields




### -field RIL_MSGPRIORITY_NORMAL



### -field RIL_MSGPRIORITY_HIGH



### -field RIL_MSGPRIORITY_URGENT



### -field RIL_MSGPRIORITY_EMERGENCY



### -field RIL_MSGPRIORITY_MAX


