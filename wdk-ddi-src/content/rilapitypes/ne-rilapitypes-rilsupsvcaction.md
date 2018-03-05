---
UID: NE:rilapitypes.RILSUPSVCACTION
title: RILSUPSVCACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcaction_2.htm
old-project: netvista
ms.assetid: 776db7b4-aa53-489d-9358-387e29e4e3e1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSUPSVCACTION, RILSUPSVCACTION enumeration [Network Drivers Starting with Windows Vista], RIL_SUPSVCACTION_DEACTIVATE, RIL_SUPSVCACTION_ERASE, RIL_SUPSVCACTION_INTERROGATE, RIL_SUPSVCACTION_MAX, RIL_SUPSVCACTION_REGISTER, RIL_SUPSVCACTION_REGISTER_PW, RIL_SUPSVCACTION_USSD, netvista.rilsupsvcaction_2, rilapitypes/RILSUPSVCACTION, rilapitypes/RIL_SUPSVCACTION_DEACTIVATE, rilapitypes/RIL_SUPSVCACTION_ERASE, rilapitypes/RIL_SUPSVCACTION_INTERROGATE, rilapitypes/RIL_SUPSVCACTION_MAX, rilapitypes/RIL_SUPSVCACTION_REGISTER, rilapitypes/RIL_SUPSVCACTION_REGISTER_PW, rilapitypes/RIL_SUPSVCACTION_USSD
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSUPSVCACTION
product: Windows
targetos: Windows
req.typenames: RILSUPSVCACTION
req.product: Windows 10 or later.
---

# RILSUPSVCACTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSUPSVCACTION { 
  RIL_SUPSVCACTION_DEACTIVATE,
  RIL_SUPSVCACTION_REGISTER,
  RIL_SUPSVCACTION_ERASE,
  RIL_SUPSVCACTION_INTERROGATE,
  RIL_SUPSVCACTION_REGISTER_PW,
  RIL_SUPSVCACTION_USSD,
  RIL_SUPSVCACTION_MAX
} RILSUPSVCACTION;
````


## -enum-fields




### -field RIL_SUPSVCACTION_ACTIVATE


### -field RIL_SUPSVCACTION_DEACTIVATE


### -field RIL_SUPSVCACTION_REGISTER


### -field RIL_SUPSVCACTION_ERASE


### -field RIL_SUPSVCACTION_INTERROGATE


### -field RIL_SUPSVCACTION_REGISTER_PW


### -field RIL_SUPSVCACTION_USSD


### -field RIL_SUPSVCACTION_MAX

