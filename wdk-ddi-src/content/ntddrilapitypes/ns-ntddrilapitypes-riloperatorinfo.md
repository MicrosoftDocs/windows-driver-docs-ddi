---
UID: NS:ntddrilapitypes.RILOPERATORINFO
title: RILOPERATORINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfo.htm
old-project: netvista
ms.assetid: 213a4d4e-d19a-40c4-9bc4-8cf6f8aa2d07
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILOPERATORINFO, RILOPERATORINFO structure [Network Drivers Starting with Windows Vista], *LPRILOPERATORINFO, RILOPERATORINFO, netvista.riloperatorinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILOPERATORINFO
product: Windows
targetos: Windows
req.typenames: RILOPERATORINFO, *LPRILOPERATORINFO
---

# RILOPERATORINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILOPERATORINFO {
  DWORD                  cbSize;
  DWORD                  dwParams;
  DWORD                  dwIndex;
  RILOPERATORINFOSTATUS  dwStatus;
  RILOPERATORNAMES       ronNames;
} RILOPERATORINFO, RILOPERATORINFO;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwIndex



### -field dwStatus



### -field ronNames


