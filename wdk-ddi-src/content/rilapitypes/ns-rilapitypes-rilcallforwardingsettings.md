---
UID: NS:rilapitypes.RILCALLFORWARDINGSETTINGS
title: RILCALLFORWARDINGSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettings_2.htm
old-project: netvista
ms.assetid: 8dacbef8-f037-4298-8a3b-cce7cf843fcf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLFORWARDINGSETTINGS, RILCALLFORWARDINGSETTINGS, *LPRILCALLFORWARDINGSETTINGS
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
req.alt-api: RILCALLFORWARDINGSETTINGS
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
req.typenames: RILCALLFORWARDINGSETTINGS, *LPRILCALLFORWARDINGSETTINGS
req.product: Windows 10 or later.
---

# RILCALLFORWARDINGSETTINGS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLFORWARDINGSETTINGS {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILSERVICESETTINGSSTATUS  dwStatus;
  DWORD                     dwInfoClasses;
  RILADDRESS                raAddress;
  RILSUBADDRESS             rsaSubAddress;
  DWORD                     dwDelayTime;
} RILCALLFORWARDINGSETTINGS, RILCALLFORWARDINGSETTINGS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwStatus


### -field dwInfoClasses


### -field raAddress


### -field rsaSubAddress


### -field dwDelayTime


## -remarks
