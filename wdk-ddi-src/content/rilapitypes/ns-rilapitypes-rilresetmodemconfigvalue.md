---
UID: NS:rilapitypes.RILRESETMODEMCONFIGVALUE
title: RILRESETMODEMCONFIGVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigvalue_2.htm
old-project: netvista
ms.assetid: 8749345c-a1a6-43f6-8cb7-f69a6734839f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRESETMODEMCONFIGVALUE structure [Network Drivers Starting with Windows Vista], RILRESETMODEMCONFIGVALUE, rilapitypes/RILRESETMODEMCONFIGVALUE, *LPRILRESETMODEMCONFIGVALUE, netvista.rilresetmodemconfigvalue_2
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
-	RILRESETMODEMCONFIGVALUE
product: Windows
targetos: Windows
req.typenames: "*LPRILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE"
req.product: Windows 10 or later.
---

# RILRESETMODEMCONFIGVALUE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRESETMODEMCONFIGVALUE {
  DWORD                                    cbSize;
  DWORD                                    dwType;
  NULL                                     RILRESETMODEMCONFIGVALUEUNION;
  RILRESETMODEMCONFIGVALUEUNION            configValueUnion;
  NULL                                     switch_is;
  NULL                                     dwType;
  BOOL                                     fValue;
  NULL                                     case;
  NULL                                     RIL_RMCV_TYPE_BOOLEAN;
  DWORD                                    dwValue;
  NULL                                     case;
  NULL                                     RIL_RMCV_TYPE_DWORD;
  WCHAR [MAXLENGTH_RESETMODEMCONFIGSTRING] wszValue;
  NULL                                     case;
  NULL                                     RIL_RMCV_TYPE_STRING;
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



#### - switch_is



#### - fValue



#### - case



#### - RIL_RMCV_TYPE_BOOLEAN



#### - dwValue



#### - RIL_RMCV_TYPE_DWORD



#### - wszValue



#### - RIL_RMCV_TYPE_STRING


