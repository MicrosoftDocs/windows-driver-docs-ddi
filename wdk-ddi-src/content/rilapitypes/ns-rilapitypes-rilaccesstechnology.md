---
UID: NS:rilapitypes.RILACCESSTECHNOLOGY
title: RILACCESSTECHNOLOGY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilaccesstechnology_2.htm
old-project: netvista
ms.assetid: e0bcbc0c-8783-43b2-a4af-3dad4aaff142
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY structure [Network Drivers Starting with Windows Vista], netvista.rilaccesstechnology_2, rilapitypes/RILACCESSTECHNOLOGY"
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
-	RILACCESSTECHNOLOGY
product: Windows
targetos: Windows
req.typenames: RILACCESSTECHNOLOGY, *LPRILACCESSTECHNOLOGY
req.product: Windows 10 or later.
---

# RILACCESSTECHNOLOGY structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILACCESSTECHNOLOGY {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwSystemType;
  NULL                          RILACCESSTECHNOLOGYKINDUNION;
  RILACCESSTECHNOLOGYKINDUNION  kindUnion;
  RILEVDOKIND                   dwEvdoKind;
  RILGSMKIND                    dwGsmKind;
  RILUMTSKIND                   dwUmtsKind;
  RILTDSCDMAKIND                dwTdscdmaKind;
  RILLTEKIND                    dwLteKind;
} RILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwSystemType


### -field kindUnion


### -field RILACCESSTECHNOLOGYKINDUNION


#### - dwEvdoKind


#### - dwGsmKind


#### - dwLteKind


#### - dwTdscdmaKind


#### - dwUmtsKind

