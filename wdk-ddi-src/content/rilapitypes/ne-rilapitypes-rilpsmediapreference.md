---
UID: NE:rilapitypes.RILPSMEDIAPREFERENCE
title: RILPSMEDIAPREFERENCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediapreference_2.htm
old-project: netvista
ms.assetid: 607c00a2-6f7e-4a68-87da-f54b8dd73b88
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILPSMEDIAPREFERENCE, RILPSMEDIAPREFERENCE enumeration [Network Drivers Starting with Windows Vista], RIL_PSMPREF_CELLONLY, RIL_PSMPREF_CELLPREFERRED, RIL_PSMPREF_NUMBER_OF_VALUES, RIL_PSMPREF_WIFIONLY, RIL_PSMPREF_WIFIPREFERRED, netvista.rilpsmediapreference_2, rilapitypes/RILPSMEDIAPREFERENCE, rilapitypes/RIL_PSMPREF_CELLONLY, rilapitypes/RIL_PSMPREF_CELLPREFERRED, rilapitypes/RIL_PSMPREF_NUMBER_OF_VALUES, rilapitypes/RIL_PSMPREF_WIFIONLY, rilapitypes/RIL_PSMPREF_WIFIPREFERRED
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
-	RILPSMEDIAPREFERENCE
product: Windows
targetos: Windows
req.typenames: RILPSMEDIAPREFERENCE
req.product: Windows 10 or later.
---

# RILPSMEDIAPREFERENCE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILPSMEDIAPREFERENCE { 
  RIL_PSMPREF_WIFIONLY,
  RIL_PSMPREF_WIFIPREFERRED,
  RIL_PSMPREF_CELLONLY,
  RIL_PSMPREF_CELLPREFERRED,
  RIL_PSMPREF_NUMBER_OF_VALUES
} RILPSMEDIAPREFERENCE;
````


## -enum-fields




### -field RIL_PSMPREF_UNKNOWN


### -field RIL_PSMPREF_WIFIONLY


### -field RIL_PSMPREF_WIFIPREFERRED


### -field RIL_PSMPREF_CELLONLY


### -field RIL_PSMPREF_CELLPREFERRED


### -field RIL_PSMPREF_NUMBER_OF_VALUES

