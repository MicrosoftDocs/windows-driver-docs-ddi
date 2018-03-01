---
UID: NS:rilapitypes.RILADDRESS
title: RILADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdress_2.htm
old-project: netvista
ms.assetid: 45888814-28c4-4cbc-ace8-7b4aa682b91b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILADDRESS, RILADDRESS, RILADDRESS structure [Network Drivers Starting with Windows Vista], netvista.riladdress_2, rilapitypes/RILADDRESS"
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
-	RILADDRESS
product: Windows
targetos: Windows
req.typenames: RILADDRESS, *LPRILADDRESS
req.product: Windows 10 or later.
---

# RILADDRESS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILADDRESS {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILADDRESSTYPE            dwType;
  RILADDRESSNUMPLAN         dwNumPlan;
  WCHAR [MAXLENGTH_ADDRESS] wszAddress;
} RILADDRESS, RILADDRESS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwType


### -field dwNumPlan


### -field wszAddress

