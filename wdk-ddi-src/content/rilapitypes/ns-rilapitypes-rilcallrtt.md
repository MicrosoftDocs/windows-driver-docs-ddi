---
UID: NS:rilapitypes.RILCALLRTT
title: RILCALLRTT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrtt.htm
old-project: netvista
ms.assetid: aa69cc11-66c7-4d23-b596-c37472af484a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILCALLRTT, RILCALLRTT, RILCALLRTT structure [Network Drivers Starting with Windows Vista], netvista.rilcallrtt, ntddrilapitypes/RILCALLRTT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCALLRTT
product: Windows
targetos: Windows
req.typenames: RILCALLRTT, *LPRILCALLRTT
req.product: Windows 10 or later.
---

# RILCALLRTT structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCALLRTT {
  RILCALLRTTACTION  dwRTTAction;
  RILCALLRTTMODE    dwRTTModeType;
  RILCALLRTTCAP     stRTTCap;
} RILCALLRTT, RILCALLRTT;
````


## -struct-fields




### -field dwRTTAction


### -field dwRTTModeType


### -field stRTTCap

