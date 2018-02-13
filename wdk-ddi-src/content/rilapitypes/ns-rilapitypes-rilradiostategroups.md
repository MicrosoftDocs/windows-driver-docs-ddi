---
UID: NS:rilapitypes.RILRADIOSTATEGROUPS
title: RILRADIOSTATEGROUPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroups_2.htm
old-project: netvista
ms.assetid: 6ef17ba4-2e87-44d6-904c-609030fe9b9b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilradiostategroups_2, RILRADIOSTATEGROUPS structure [Network Drivers Starting with Windows Vista], RILRADIOSTATEGROUPS, rilapitypes/RILRADIOSTATEGROUPS, *LPRILRADIOSTATEGROUPS
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
-	RILRADIOSTATEGROUPS
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEGROUPS, *LPRILRADIOSTATEGROUPS
req.product: Windows 10 or later.
---

# RILRADIOSTATEGROUPS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRADIOSTATEGROUPS {
  DWORD                  dwCntGroups;
  RILRADIOSTATEGROUP [1] rilGroups;
} RILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS;
````


## -struct-fields




### -field dwCntGroups


### -field rilGroups

