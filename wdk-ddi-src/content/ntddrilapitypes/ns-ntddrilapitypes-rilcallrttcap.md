---
UID: NS:ntddrilapitypes.RILCALLRTTCAP
title: RILCALLRTTCAP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrttcap.htm
old-project: netvista
ms.assetid: 7cb8618b-93da-4b6d-8f03-fb42a8d28fd0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLRTTCAP structure [Network Drivers Starting with Windows Vista], netvista.rilcallrttcap, RILCALLRTTCAP, *LPRILCALLRTTCAP, ntddrilapitypes/RILCALLRTTCAP
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
-	RILCALLRTTCAP
product: Windows
targetos: Windows
req.typenames: *LPRILCALLRTTCAP, RILCALLRTTCAP
---

# RILCALLRTTCAP structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCALLRTTCAP {
  RILCALLRTTMODE  dwLocalRTTCap;
  RILCALLRTTMODE  dwPeerRTTCap;
} RILCALLRTTCAP, RILCALLRTTCAP;
````


## -struct-fields




### -field dwLocalRTTCap



### -field dwPeerRTTCap


