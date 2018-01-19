---
UID: NS:rilapitypes.RILACCESSTECHNOLOGY
title: RILACCESSTECHNOLOGY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilaccesstechnology_2.htm
old-project: netvista
ms.assetid: e0bcbc0c-8783-43b2-a4af-3dad4aaff142
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILACCESSTECHNOLOGY, RILACCESSTECHNOLOGY, *LPRILACCESSTECHNOLOGY
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
req.alt-api: RILACCESSTECHNOLOGY
req.alt-loc: rilapitypes.h
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


### -field RILACCESSTECHNOLOGYKINDUNION


### -field kindUnion


### -field dwEvdoKind


### -field dwGsmKind


### -field dwUmtsKind


### -field dwTdscdmaKind


### -field dwLteKind


## -remarks
