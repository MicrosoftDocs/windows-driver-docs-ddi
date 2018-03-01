---
UID: NE:oemrilapitypes.RILGETTOKENPARAMMASK
title: RILGETTOKENPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgettokenparammask.htm
old-project: netvista
ms.assetid: d791b497-3ef3-42f1-a6e6-980992c97f45
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILDEVSPECIFICPARAMMASK, RILDEVSPECIFICPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILGETTOKENPARAMMASK, RILGETTOKENPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_GETTOKEN_ALL, RIL_PARAM_GETTOKEN_HEADER, RIL_PARAM_GETTOKEN_PROTOCOL_ID, RIL_PARAM_GETTOKEN_TIMEOUT, netvista.rilgettokenparammask, oemrilapitypes/RILGETTOKENPARAMMASK, oemrilapitypes/RIL_PARAM_GETTOKEN_ALL, oemrilapitypes/RIL_PARAM_GETTOKEN_HEADER, oemrilapitypes/RIL_PARAM_GETTOKEN_PROTOCOL_ID, oemrilapitypes/RIL_PARAM_GETTOKEN_TIMEOUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: oemrilapitypes.h
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	oemrilapitypes.h
api_name:
-	RILDEVSPECIFICPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDEVSPECIFICPARAMMASK
---

# RILGETTOKENPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILDEVSPECIFICPARAMMASK { 
  RIL_PARAM_GETTOKEN_TIMEOUT,
  RIL_PARAM_GETTOKEN_HEADER,
  RIL_PARAM_GETTOKEN_PROTOCOL_ID,
  RIL_PARAM_GETTOKEN_ALL
} RILDEVSPECIFICPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_GETTOKEN_TIMEOUT


### -field RIL_PARAM_GETTOKEN_HEADER


### -field RIL_PARAM_GETTOKEN_PROTOCOL_ID


### -field RIL_PARAM_GETTOKEN_ALL

