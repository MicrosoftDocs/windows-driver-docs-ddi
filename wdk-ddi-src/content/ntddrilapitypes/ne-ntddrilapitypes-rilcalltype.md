---
UID: NE:ntddrilapitypes.RILCALLTYPE
title: RILCALLTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalltype.htm
old-project: netvista
ms.assetid: bd6b9e57-f50b-4743-9c51-066940aad200
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLTYPE_USSD, ntddrilapitypes/RIL_CALLTYPE_SUPSVC, RILCALLTYPE, ntddrilapitypes/RIL_CALLTYPE_FAX, ntddrilapitypes/RIL_CALLTYPE_IMS, ntddrilapitypes/RIL_CALLTYPE_DATA, RIL_CALLTYPE_DATA, RIL_CALLTYPE_IMS, netvista.rilcalltype, ntddrilapitypes/RILCALLTYPE, ntddrilapitypes/RIL_CALLTYPE_MAX, RIL_CALLTYPE_FAX, RIL_CALLTYPE_VOICE, RIL_CALLTYPE_MAX, RIL_CALLTYPE_PTT, ntddrilapitypes/RIL_CALLTYPE_VOICE, ntddrilapitypes/RIL_CALLTYPE_PTT, ntddrilapitypes/RIL_CALLTYPE_VT, ntddrilapitypes/RIL_CALLTYPE_USSD, RIL_CALLTYPE_VT, RILCALLTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLTYPE_SUPSVC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILCALLTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLTYPE
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



#### - RIL_CALLTYPE_VOICE



#### - RIL_CALLTYPE_DATA



#### - RIL_CALLTYPE_FAX



#### - RIL_CALLTYPE_PTT



#### - RIL_CALLTYPE_VT



#### - RIL_CALLTYPE_USSD



#### - RIL_CALLTYPE_SUPSVC



#### - RIL_CALLTYPE_IMS



#### - RIL_CALLTYPE_MAX


