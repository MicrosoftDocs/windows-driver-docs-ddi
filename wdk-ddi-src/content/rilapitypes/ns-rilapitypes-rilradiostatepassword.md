---
UID: NS:rilapitypes.RILRADIOSTATEPASSWORD
title: RILRADIOSTATEPASSWORD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostatepassword_2.htm
old-project: netvista
ms.assetid: 879f38f7-ae13-4a39-bc68-b5c5f5f4f32c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD, *LPRILRADIOSTATEPASSWORD
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
req.alt-api: RILRADIOSTATEPASSWORD
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
req.typenames: RILRADIOSTATEPASSWORD, *LPRILRADIOSTATEPASSWORD
req.product: Windows 10 or later.
---

# RILRADIOSTATEPASSWORD structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILRADIOSTATEPASSWORD {
  DWORD                                 dwPasswordId;
  WCHAR [MAXLENGTH_RADIOPASSWORD_WCHAR] wszPassword;
} RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD;
````


## -struct-fields

### -field dwPasswordId


### -field wszPassword


## -remarks
