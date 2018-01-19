---
UID: NS:rilapitypes.RILMSGDCS
title: RILMSGDCS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcs_2.htm
old-project: netvista
ms.assetid: 50ef03af-3890-40dd-b0ed-7cf048f8530d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGDCS, *LPRILMSGDCS, RILMSGDCS
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
req.alt-api: RILMSGDCS
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
req.typenames: *LPRILMSGDCS, RILMSGDCS
req.product: Windows 10 or later.
---

# RILMSGDCS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILMSGDCS {
  DWORD                cbSize;
  DWORD                dwParams;
  RILMSGDCSTYPE        dwType;
  DWORD                dwFlags;
  RILMSGDCSMSGCLASS    dwMsgClass;
  RILMSGDCSALPHABET    dwAlphabet;
  RILMSGDCSINDICATION  dwIndication;
  DWORD                dwLanguage;
} RILMSGDCS, RILMSGDCS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwType


### -field dwFlags


### -field dwMsgClass


### -field dwAlphabet


### -field dwIndication


### -field dwLanguage


## -remarks
