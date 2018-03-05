---
UID: NE:rilapitypes.RIL3GPPTONE
title: RIL3GPPTONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpptone_2.htm
old-project: netvista
ms.assetid: 05981a37-ce5c-4214-82b7-c8705102bd6a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL3GPPTONE, RIL3GPPTONE enumeration [Network Drivers Starting with Windows Vista], RIL_3GPPTONE_AUTHENTICATIONFAILURE, RIL_3GPPTONE_BUSY, RIL_3GPPTONE_CALLDROPPED, RIL_3GPPTONE_CONGESTION, RIL_3GPPTONE_MAX, RIL_3GPPTONE_NUMBERUNOBTAINABLE, RIL_3GPPTONE_RINGBACK, netvista.ril3gpptone_2, rilapitypes/RIL3GPPTONE, rilapitypes/RIL_3GPPTONE_AUTHENTICATIONFAILURE, rilapitypes/RIL_3GPPTONE_BUSY, rilapitypes/RIL_3GPPTONE_CALLDROPPED, rilapitypes/RIL_3GPPTONE_CONGESTION, rilapitypes/RIL_3GPPTONE_MAX, rilapitypes/RIL_3GPPTONE_NUMBERUNOBTAINABLE, rilapitypes/RIL_3GPPTONE_RINGBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RIL3GPPTONE
product: Windows
targetos: Windows
req.typenames: RIL3GPPTONE
req.product: Windows 10 or later.
---

# RIL3GPPTONE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RIL3GPPTONE { 
  RIL_3GPPTONE_RINGBACK,
  RIL_3GPPTONE_BUSY,
  RIL_3GPPTONE_CONGESTION,
  RIL_3GPPTONE_AUTHENTICATIONFAILURE,
  RIL_3GPPTONE_NUMBERUNOBTAINABLE,
  RIL_3GPPTONE_CALLDROPPED,
  RIL_3GPPTONE_MAX
} RIL3GPPTONE;
````


## -enum-fields




### -field RIL_3GPPTONE_TONEOFF


### -field RIL_3GPPTONE_RINGBACK


### -field RIL_3GPPTONE_BUSY


### -field RIL_3GPPTONE_CONGESTION


### -field RIL_3GPPTONE_AUTHENTICATIONFAILURE


### -field RIL_3GPPTONE_NUMBERUNOBTAINABLE


### -field RIL_3GPPTONE_CALLDROPPED


### -field RIL_3GPPTONE_MAX

