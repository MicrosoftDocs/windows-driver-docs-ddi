---
UID: NS:rilapitypes.RILUICCAPPDATACHANGE
title: RILUICCAPPDATACHANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachange_2.htm
old-project: netvista
ms.assetid: b812cd5d-73a1-42bc-a1ae-1c1494369288
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCAPPDATACHANGE, *LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE
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
req.alt-api: RILUICCAPPDATACHANGE
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
req.typenames: *LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE
req.product: Windows 10 or later.
---

# RILUICCAPPDATACHANGE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCAPPDATACHANGE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILUICCAPPDATACHANGEENUM  dwDataChange;
} RILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE;
````


## -struct-fields

### -field cbSize


### -field hUiccApp


### -field dwDataChange


## -remarks
