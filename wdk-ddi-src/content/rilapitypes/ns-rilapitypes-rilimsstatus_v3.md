---
UID: NS:rilapitypes.RILIMSSTATUS_V3
title: RILIMSSTATUS_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v3_2.htm
old-project: netvista
ms.assetid: 7ae2e97d-d055-412f-a219-258780319797
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILIMSSTATUS_V3, RILIMSSTATUS, *LPRILIMSSTATUS_V3, *LPRILIMSSTATUS, RILIMSSTATUS_V3
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
req.alt-api: RILIMSSTATUS_V3
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
req.typenames: RILIMSSTATUS, *LPRILIMSSTATUS_V3, *LPRILIMSSTATUS, RILIMSSTATUS_V3
req.product: Windows 10 or later.
---

# RILIMSSTATUS_V3 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILIMSSTATUS_V3 {
  DWORD                     cbSize;
  DWORD                     dwParams;
  DWORD                     dwExecutor;
  HUICCAPP                  hUiccApp;
  DWORD                     dwAvailableServices;
  RILSMSFORMAT              dwSMSSupportedFormat;
  WCHAR [MAXLENGTH_ADDRESS] wszServingDomain;
  RILIMSSYSTEMTYPE          dwIMSSystemType;
} RILIMSSTATUS_V3, RILIMSSTATUS_V3;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwAvailableServices


### -field dwSMSSupportedFormat


### -field wszServingDomain


### -field dwIMSSystemType


## -remarks
