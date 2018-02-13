---
UID: NE:rilapitypes.RILREMOTEPARTYINFOVALUE
title: RILREMOTEPARTYINFOVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfovalue_2.htm
old-project: netvista
ms.assetid: bdea158f-6ee5-4e59-be50-efd8027a8645
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_REMOTEPARTYINFO_UNAVAILABLE, RILREMOTEPARTYINFOVALUE, netvista.rilremotepartyinfovalue_2, rilapitypes/RIL_REMOTEPARTYINFO_WITHHELD, rilapitypes/RIL_REMOTEPARTYINFO_UNAVAILABLE, RIL_REMOTEPARTYINFO_MAX, rilapitypes/RIL_REMOTEPARTYINFO_MAX, rilapitypes/RILREMOTEPARTYINFOVALUE, RIL_REMOTEPARTYINFO_WITHHELD, RILREMOTEPARTYINFOVALUE enumeration [Network Drivers Starting with Windows Vista]
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
-	RILREMOTEPARTYINFOVALUE
product: Windows
targetos: Windows
req.typenames: RILREMOTEPARTYINFOVALUE
req.product: Windows 10 or later.
---

# RILREMOTEPARTYINFOVALUE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILREMOTEPARTYINFOVALUE { 
  RIL_REMOTEPARTYINFO_WITHHELD,
  RIL_REMOTEPARTYINFO_UNAVAILABLE,
  RIL_REMOTEPARTYINFO_MAX
} RILREMOTEPARTYINFOVALUE;
````


## -enum-fields




### -field RIL_REMOTEPARTYINFO_VALID


### -field RIL_REMOTEPARTYINFO_WITHHELD


### -field RIL_REMOTEPARTYINFO_UNAVAILABLE


### -field RIL_REMOTEPARTYINFO_MAX

