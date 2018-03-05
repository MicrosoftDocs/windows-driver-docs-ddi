---
UID: NS:rilapitypes.RILPHONEBOOKADDITIONALNUMBERINFO
title: RILPHONEBOOKADDITIONALNUMBERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberinfo_2.htm
old-project: netvista
ms.assetid: c56dc6df-e547-42f4-9656-01de5e66909a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookadditionalnumberinfo_2, rilapitypes/RILPHONEBOOKADDITIONALNUMBERINFO"
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
-	RILPHONEBOOKADDITIONALNUMBERINFO
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBERINFO, *LPRILPHONEBOOKADDITIONALNUMBERINFO
req.product: Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBERINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPHONEBOOKADDITIONALNUMBERINFO {
  DWORD                                  cbSize;
  DWORD                                  dwRilPBANSSize;
  RILPHONEBOOKADDITIONALNUMBERSTRING [1] RilPBANS;
} RILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO;
````


## -struct-fields




### -field cbSize


### -field dwRilPBANSSize


### -field RilPBANS

