---
UID: NS:rilapitypes.RILSETCELLBROADCASTMSGCONFIGPARAMS
title: RILSETCELLBROADCASTMSGCONFIGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcellbroadcastmsgconfigparams_2.htm
old-project: netvista
ms.assetid: 978d3efa-23bb-4fa8-b879-9714813880be
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSETCELLBROADCASTMSGCONFIGPARAMS, netvista.rilsetcellbroadcastmsgconfigparams_2, rilapitypes/RILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS structure [Network Drivers Starting with Windows Vista]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILSETCELLBROADCASTMSGCONFIGPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS"
req.product: Windows 10 or later.
---

# RILSETCELLBROADCASTMSGCONFIGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSETCELLBROADCASTMSGCONFIGPARAMS {
  HUICCAPP        hUiccApp;
  RILCBMSGCONFIG  rmCBConfig;
} RILSETCELLBROADCASTMSGCONFIGPARAMS, RILSETCELLBROADCASTMSGCONFIGPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field rmCBConfig

