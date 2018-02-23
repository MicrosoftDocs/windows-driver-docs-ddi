---
UID: NE:rilapitypes.RILDIALEDIDSETTINGSPARAMMASK
title: RILDIALEDIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialedidsettingsparammask_2.htm
old-project: netvista
ms.assetid: c69d03b7-ef07-41b3-9659-79ab05ecd4e9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rildialedidsettingsparammask_2, RIL_PARAM_DIDS_STATUS, rilapitypes/RIL_PARAM_DIDS_ALL, RIL_PARAM_DIDS_ALL, RILDIALEDIDSETTINGSPARAMMASK, rilapitypes/RILDIALEDIDSETTINGSPARAMMASK, rilapitypes/RIL_PARAM_DIDS_STATUS, RIL_PARAM_DIDS_PROVISIONING, RILDIALEDIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_DIDS_PROVISIONING
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
-	RILDIALEDIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDIALEDIDSETTINGSPARAMMASK
req.product: Windows 10 or later.
---

# RILDIALEDIDSETTINGSPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILDIALEDIDSETTINGSPARAMMASK { 
  RIL_PARAM_DIDS_PROVISIONING,
  RIL_PARAM_DIDS_STATUS,
  RIL_PARAM_DIDS_ALL
} RILDIALEDIDSETTINGSPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_DIDS_EXECUTOR


### -field RIL_PARAM_DIDS_PROVISIONING


### -field RIL_PARAM_DIDS_STATUS


### -field RIL_PARAM_DIDS_ALL

