---
UID: NS:rilapitypes.RILRADIOCONFIGURATIONS
title: RILRADIOCONFIGURATIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradioconfigurations_2.htm
old-project: netvista
ms.assetid: fdd53162-b884-4360-b80a-14225abc1185
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRADIOCONFIGURATIONS structure [Network Drivers Starting with Windows Vista], netvista.rilradioconfigurations_2, RILRADIOCONFIGURATIONS, rilapitypes/RILRADIOCONFIGURATIONS, *LPRILRADIOCONFIGURATIONS
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
-	RILRADIOCONFIGURATIONS
product: Windows
targetos: Windows
req.typenames: RILRADIOCONFIGURATIONS, *LPRILRADIOCONFIGURATIONS
req.product: Windows 10 or later.
---

# RILRADIOCONFIGURATIONS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRADIOCONFIGURATIONS {
  DWORD                     dwNumberOfConfigurations;
  RILRADIOCONFIGURATION [1] stConfigurations;
} RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS;
````


## -struct-fields




#### - dwNumberOfConfigurations



#### - stConfigurations


