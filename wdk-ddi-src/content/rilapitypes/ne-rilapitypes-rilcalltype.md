---
UID: NE:rilapitypes.RILCALLTYPE
title: RILCALLTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalltype_2.htm
old-project: netvista
ms.assetid: 16688917-77d4-4ca1-a4e0-357da16b55c0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLTYPE, RILCALLTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLTYPE_DATA, RIL_CALLTYPE_FAX, RIL_CALLTYPE_IMS, RIL_CALLTYPE_MAX, RIL_CALLTYPE_PTT, RIL_CALLTYPE_SUPSVC, RIL_CALLTYPE_USSD, RIL_CALLTYPE_VOICE, RIL_CALLTYPE_VT, netvista.rilcalltype_2, rilapitypes/RILCALLTYPE, rilapitypes/RIL_CALLTYPE_DATA, rilapitypes/RIL_CALLTYPE_FAX, rilapitypes/RIL_CALLTYPE_IMS, rilapitypes/RIL_CALLTYPE_MAX, rilapitypes/RIL_CALLTYPE_PTT, rilapitypes/RIL_CALLTYPE_SUPSVC, rilapitypes/RIL_CALLTYPE_USSD, rilapitypes/RIL_CALLTYPE_VOICE, rilapitypes/RIL_CALLTYPE_VT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLTYPE
req.product: Windows 10 or later.
---

# RILCALLTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLTYPE { 
  RIL_CALLTYPE_VOICE,
  RIL_CALLTYPE_DATA,
  RIL_CALLTYPE_FAX,
  RIL_CALLTYPE_PTT,
  RIL_CALLTYPE_VT,
  RIL_CALLTYPE_USSD,
  RIL_CALLTYPE_SUPSVC,
  RIL_CALLTYPE_IMS,
  RIL_CALLTYPE_MAX
} RILCALLTYPE;
````


## -enum-fields




### -field RIL_CALLTYPE_UNKNOWN


### -field RIL_CALLTYPE_VOICE


### -field RIL_CALLTYPE_DATA


### -field RIL_CALLTYPE_FAX


### -field RIL_CALLTYPE_PTT


### -field RIL_CALLTYPE_VT


### -field RIL_CALLTYPE_USSD


### -field RIL_CALLTYPE_SUPSVC


### -field RIL_CALLTYPE_IMS


### -field RIL_CALLTYPE_MAX

