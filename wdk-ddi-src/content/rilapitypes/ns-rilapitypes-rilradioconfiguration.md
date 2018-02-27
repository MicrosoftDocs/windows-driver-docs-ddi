---
UID: NS:rilapitypes.RILRADIOCONFIGURATION
title: RILRADIOCONFIGURATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradioconfiguration_2.htm
old-project: netvista
ms.assetid: bdd43d7d-a526-4a3a-81fc-561ae99d467e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILRADIOCONFIGURATION, RILRADIOCONFIGURATION, RILRADIOCONFIGURATION structure [Network Drivers Starting with Windows Vista], netvista.rilradioconfiguration_2, rilapitypes/RILRADIOCONFIGURATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
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
-	RILRADIOCONFIGURATION
product: Windows
targetos: Windows
req.typenames: RILRADIOCONFIGURATION, *LPRILRADIOCONFIGURATION
req.product: Windows 10 or later.
---

# RILRADIOCONFIGURATION structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRADIOCONFIGURATION {
  DWORD                           dwConfigId;
  RILRADIOCONFIGURATIONRADIOTYPE  dwRadioType;
  DWORD [MAXNUM_EXECUTORS]        dwSystemTypes;
} RILRADIOCONFIGURATION, RILRADIOCONFIGURATION;
````


## -struct-fields




### -field dwConfigId


### -field dwRadioType


### -field dwSystemTypes

