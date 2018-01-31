---
UID: NS:ntddrilapitypes.RILRESETMODEMCONFIGVALUE
title: RILRESETMODEMCONFIGVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigvalue.htm
old-project: netvista
ms.assetid: 48068d1d-3fe7-4bd6-8c91-094e4187ca1f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRESETMODEMCONFIGVALUE structure [Network Drivers Starting with Windows Vista], RILRESETMODEMCONFIGVALUE, *LPRILRESETMODEMCONFIGVALUE, netvista.rilresetmodemconfigvalue, ntddrilapitypes/RILRESETMODEMCONFIGVALUE
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
-	RILRESETMODEMCONFIGVALUE
product: Windows
targetos: Windows
req.typenames: "*LPRILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE"
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




#### - configValueUnion



### -field configValueUnion.fValue

 


### -field configValueUnion.dwValue

 


### -field configValueUnion.wszValue

 


#### - RILRESETMODEMCONFIGVALUEUNION



#### - cbSize



#### - dwType



#### - fValue



#### - dwValue



#### - wszValue


