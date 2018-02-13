---
UID: NS:rilapitypes.RILCALLRTT
title: RILCALLRTT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrtt_2.htm
old-project: netvista
ms.assetid: e11103c6-665f-4673-8c53-5b35abf0299d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallrtt_2, rilapitypes/RILCALLRTT, RILCALLRTT structure [Network Drivers Starting with Windows Vista], *LPRILCALLRTT, RILCALLRTT
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

