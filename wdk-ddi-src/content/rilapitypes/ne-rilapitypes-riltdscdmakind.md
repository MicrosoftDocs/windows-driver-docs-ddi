---
UID: NE:rilapitypes.RILTDSCDMAKIND
title: RILTDSCDMAKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltdscdmakind_2.htm
old-project: netvista
ms.assetid: ff6c4459-dd3e-43f6-aa41-a2e82221394e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.riltdscdmakind_2, RILTDSCDMAKIND, RILTDSCDMAKIND enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_TDSCDMAKIND_HSDPA, RIL_TDSCDMAKIND_MAX, RIL_TDSCDMAKIND_HSDPA, RIL_TDSCDMAKIND_HSPAPLUS, rilapitypes/RIL_TDSCDMAKIND_HSUPA, rilapitypes/RIL_TDSCDMAKIND_DC_HSPAPLUS, rilapitypes/RILTDSCDMAKIND, RIL_TDSCDMAKIND_HSUPA, RIL_TDSCDMAKIND_DC_HSPAPLUS, rilapitypes/RIL_TDSCDMAKIND_MAX, rilapitypes/RIL_TDSCDMAKIND_HSPAPLUS
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
-	RILTDSCDMAKIND
product: Windows
targetos: Windows
req.typenames: RILTDSCDMAKIND
req.product: Windows 10 or later.
---

# RILTDSCDMAKIND enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILTDSCDMAKIND { 
  RIL_TDSCDMAKIND_HSDPA,
  RIL_TDSCDMAKIND_HSUPA,
  RIL_TDSCDMAKIND_HSPAPLUS,
  RIL_TDSCDMAKIND_DC_HSPAPLUS,
  RIL_TDSCDMAKIND_MAX
} RILTDSCDMAKIND;
````


## -enum-fields




### -field RIL_TDSCDMAKIND_UMTS



### -field RIL_TDSCDMAKIND_HSDPA



### -field RIL_TDSCDMAKIND_HSUPA



### -field RIL_TDSCDMAKIND_HSPAPLUS



### -field RIL_TDSCDMAKIND_DC_HSPAPLUS



### -field RIL_TDSCDMAKIND_MAX


