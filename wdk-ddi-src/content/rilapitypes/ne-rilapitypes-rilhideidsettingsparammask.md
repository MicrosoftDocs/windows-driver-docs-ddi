---
UID: NE:rilapitypes.RILHIDEIDSETTINGSPARAMMASK
title: RILHIDEIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideidsettingsparammask_2.htm
old-project: netvista
ms.assetid: 5c951b21-1fa9-4b76-8631-3ab4148176ef
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILHIDEIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_HIDS_STATUS, RIL_PARAM_HIDS_STATUS, RILHIDEIDSETTINGSPARAMMASK, rilapitypes/RIL_PARAM_HIDS_PROVISIONING, rilapitypes/RIL_PARAM_HIDS_ALL, netvista.rilhideidsettingsparammask_2, RIL_PARAM_HIDS_PROVISIONING, rilapitypes/RILHIDEIDSETTINGSPARAMMASK, RIL_PARAM_HIDS_ALL
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



#### - RIL_PARAM_HIDS_STATUS



#### - RIL_PARAM_HIDS_PROVISIONING



#### - RIL_PARAM_HIDS_ALL


