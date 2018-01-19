---
UID: NS:ntddrilapitypes.RILRESETMODEMCONFIGVALUE
title: RILRESETMODEMCONFIGVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigvalue.htm
old-project: netvista
ms.assetid: 48068d1d-3fe7-4bd6-8c91-094e4187ca1f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRESETMODEMCONFIGVALUE, *LPRILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE
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
req.alt-api: RILRESETMODEMCONFIGVALUE
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
req.typenames: *LPRILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE
---

# RILRESETMODEMCONFIGVALUE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRESETMODEMCONFIGVALUE {
  DWORD                          cbSize;
  DWORD                          dwType;
  NULL                           RILRESETMODEMCONFIGVALUEUNION;
  RILRESETMODEMCONFIGVALUEUNION  configValueUnion;
  BOOL                           fValue;
  DWORD                          dwValue;
  WCHAR [256]                    wszValue;
} RILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE;
````


## -struct-fields

### -field cbSize


### -field dwType


### -field RILRESETMODEMCONFIGVALUEUNION


### -field configValueUnion


### -field fValue


### -field dwValue


### -field wszValue


## -remarks
