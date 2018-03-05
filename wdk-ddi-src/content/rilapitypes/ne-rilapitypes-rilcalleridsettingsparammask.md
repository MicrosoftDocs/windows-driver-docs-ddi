---
UID: NE:rilapitypes.RILCALLERIDSETTINGSPARAMMASK
title: RILCALLERIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalleridsettingsparammask_2.htm
old-project: netvista
ms.assetid: 579165ca-94e7-433c-91c6-3112c4b75f64
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCALLERIDSETTINGSPARAMMASK, RILCALLERIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CIDS_ALL, RIL_PARAM_CIDS_PROVISIONING, RIL_PARAM_CIDS_STATUS, netvista.rilcalleridsettingsparammask_2, rilapitypes/RILCALLERIDSETTINGSPARAMMASK, rilapitypes/RIL_PARAM_CIDS_ALL, rilapitypes/RIL_PARAM_CIDS_PROVISIONING, rilapitypes/RIL_PARAM_CIDS_STATUS
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
-	RILCALLERIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLERIDSETTINGSPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLERIDSETTINGSPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLERIDSETTINGSPARAMMASK { 
  RIL_PARAM_CIDS_PROVISIONING,
  RIL_PARAM_CIDS_STATUS,
  RIL_PARAM_CIDS_ALL
} RILCALLERIDSETTINGSPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_CIDS_EXECUTOR


### -field RIL_PARAM_CIDS_PROVISIONING


### -field RIL_PARAM_CIDS_STATUS


### -field RIL_PARAM_CIDS_ALL

