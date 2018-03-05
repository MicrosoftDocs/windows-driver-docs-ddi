---
UID: NE:rilapitypes.RILHIDEIDSETTINGSPARAMMASK
title: RILHIDEIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideidsettingsparammask_2.htm
old-project: netvista
ms.assetid: 5c951b21-1fa9-4b76-8631-3ab4148176ef
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILHIDEIDSETTINGSPARAMMASK, RILHIDEIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_HIDS_ALL, RIL_PARAM_HIDS_PROVISIONING, RIL_PARAM_HIDS_STATUS, netvista.rilhideidsettingsparammask_2, rilapitypes/RILHIDEIDSETTINGSPARAMMASK, rilapitypes/RIL_PARAM_HIDS_ALL, rilapitypes/RIL_PARAM_HIDS_PROVISIONING, rilapitypes/RIL_PARAM_HIDS_STATUS
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
-	RILHIDEIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILHIDEIDSETTINGSPARAMMASK
req.product: Windows 10 or later.
---

# RILHIDEIDSETTINGSPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILHIDEIDSETTINGSPARAMMASK { 
  RIL_PARAM_HIDS_STATUS,
  RIL_PARAM_HIDS_PROVISIONING,
  RIL_PARAM_HIDS_ALL
} RILHIDEIDSETTINGSPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_HIDS_EXECUTOR


### -field RIL_PARAM_HIDS_STATUS


### -field RIL_PARAM_HIDS_PROVISIONING


### -field RIL_PARAM_HIDS_ALL

