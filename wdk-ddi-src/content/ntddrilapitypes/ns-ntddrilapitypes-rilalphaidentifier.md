---
UID: NS:ntddrilapitypes.RILALPHAIDENTIFIER
title: RILALPHAIDENTIFIER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilalphaidentifier.htm
old-project: netvista
ms.assetid: 2f7e8df5-31ae-4e1a-8dbb-89bfe8fc422d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILALPHAIDENTIFIER, RILALPHAIDENTIFIER, *LPRILALPHAIDENTIFIER
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
req.alt-api: RILALPHAIDENTIFIER
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILALPHAIDENTIFIER, *LPRILALPHAIDENTIFIER
---

# RILALPHAIDENTIFIER structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILALPHAIDENTIFIER {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILALPHAIDENTIFIDERTYPE  dwType;
  WCHAR [256]              wszReason;
} RILALPHAIDENTIFIER, RILALPHAIDENTIFIER;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwType


### -field wszReason


## -remarks
