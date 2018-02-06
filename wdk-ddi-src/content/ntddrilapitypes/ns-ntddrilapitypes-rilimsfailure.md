---
UID: NS:ntddrilapitypes.RILIMSFAILURE
title: RILIMSFAILURE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailure.htm
old-project: netvista
ms.assetid: 8be10470-3761-4120-8987-00d6fcc9a989
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilimsfailure, ntddrilapitypes/RILIMSFAILURE, RILIMSFAILURE structure [Network Drivers Starting with Windows Vista], *LPRILIMSFAILURE, RILIMSFAILURE
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
-	RILIMSFAILURE
product: Windows
targetos: Windows
req.typenames: "*LPRILIMSFAILURE, RILIMSFAILURE"
---

# RILIMSFAILURE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILIMSFAILURE {
  DWORD                     cbSize;
  DWORD                     dwParams;
  DWORD                     dwExecutor;
  RILIMSFAILUREMESSAGETYPE  dwMessageType;
  DWORD                     dwMessageSubType;
  DWORD                     dwErrorCode;
  WCHAR [256]               wszErrorString;
} RILIMSFAILURE, RILIMSFAILURE;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwExecutor



### -field dwMessageType



### -field dwMessageSubType



### -field dwErrorCode



### -field wszErrorString


