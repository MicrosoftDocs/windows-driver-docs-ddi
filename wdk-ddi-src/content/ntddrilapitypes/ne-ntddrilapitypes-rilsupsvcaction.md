---
UID: NE:ntddrilapitypes.RILSUPSVCACTION
title: RILSUPSVCACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcaction.htm
old-project: netvista
ms.assetid: 14c9b97d-7f3f-45ef-9be2-c36495c69081
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SUPSVCACTION_INTERROGATE, ntddrilapitypes/RIL_SUPSVCACTION_MAX, ntddrilapitypes/RIL_SUPSVCACTION_REGISTER_PW, RIL_SUPSVCACTION_REGISTER, RIL_SUPSVCACTION_MAX, ntddrilapitypes/RIL_SUPSVCACTION_DEACTIVATE, RIL_SUPSVCACTION_REGISTER_PW, RIL_SUPSVCACTION_USSD, ntddrilapitypes/RIL_SUPSVCACTION_USSD, netvista.rilsupsvcaction, RIL_SUPSVCACTION_DEACTIVATE, ntddrilapitypes/RIL_SUPSVCACTION_ERASE, RIL_SUPSVCACTION_ERASE, ntddrilapitypes/RILSUPSVCACTION, ntddrilapitypes/RIL_SUPSVCACTION_INTERROGATE, RILSUPSVCACTION, RILSUPSVCACTION enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_SUPSVCACTION_REGISTER
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
-	RILSUPSVCACTION
product: Windows
targetos: Windows
req.typenames: RILSUPSVCACTION
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


