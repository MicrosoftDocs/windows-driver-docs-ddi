---
UID: NS:rilapitypes.RILRADIOSTATEITEMS
title: RILRADIOSTATEITEMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitems_2.htm
old-project: netvista
ms.assetid: 41f8c9fc-7793-47c8-b381-4ef59dfde6b8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilradiostateitems_2, RILRADIOSTATEITEMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILRADIOSTATEITEMS, *LPRILRADIOSTATEITEMS, RILRADIOSTATEITEMS
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
-	RILRADIOSTATEITEMS
product: Windows
targetos: Windows
req.typenames: "*LPRILRADIOSTATEITEMS, RILRADIOSTATEITEMS"
req.product: Windows 10 or later.
---

# RILRADIOSTATEITEMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRADIOSTATEITEMS {
  DWORD                 dwGroupId;
  DWORD                 dwCntItems;
  RILRADIOSTATEITEM [1] rilItems;
} RILRADIOSTATEITEMS, RILRADIOSTATEITEMS;
````


## -struct-fields




### -field dwGroupId



### -field dwCntItems



### -field rilItems


