---
UID: NS:rilapitypes.RILUICCLOCKCREDENTIAL
title: RILUICCLOCKCREDENTIAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockcredential_2.htm
old-project: netvista
ms.assetid: bb7b3075-c424-4a8b-bff9-64cdb85218a2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCLOCKCREDENTIAL, *LPRILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL
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
req.alt-api: RILUICCLOCKCREDENTIAL
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
req.typenames: *LPRILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL
req.product: Windows 10 or later.
---

# RILUICCLOCKCREDENTIAL structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCLOCKCREDENTIAL {
  RILUICCLOCK               rilUiccLock;
  char [MAXLENGTH_PASSWORD] szPassword;
} RILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL;
````


## -struct-fields

### -field rilUiccLock


### -field szPassword


## -remarks
