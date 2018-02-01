---
UID: NS:rilapitypes.RILACCESSTECHNOLOGY
title: RILACCESSTECHNOLOGY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilaccesstechnology_2.htm
old-project: netvista
ms.assetid: e0bcbc0c-8783-43b2-a4af-3dad4aaff142
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilaccesstechnology_2, rilapitypes/RILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY structure [Network Drivers Starting with Windows Vista], RILACCESSTECHNOLOGY, *LPRILACCESSTECHNOLOGY
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
req.typenames: "*LPRILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY"
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




### -field kindUnion



### -field kindUnion.dwEvdoKind

 


### -field kindUnion.dwGsmKind

 


### -field kindUnion.dwUmtsKind

 


### -field kindUnion.dwTdscdmaKind

 


### -field kindUnion.dwLteKind

 


### -field RILACCESSTECHNOLOGYKINDUNION



### -field cbSize



### -field dwParams



### -field dwSystemType



#### - dwEvdoKind



#### - dwGsmKind



#### - dwLteKind



#### - dwTdscdmaKind



#### - dwUmtsKind


