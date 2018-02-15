---
UID: NE:rilapitypes.RIL3GPP2TONE
title: RIL3GPP2TONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpp2tone_2.htm
old-project: netvista
ms.assetid: 306efd49-27ca-43d1-8f56-2f93c31be9a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril3gpp2tone_2, rilapitypes/RIL_3GPP2TONE_REORDER, rilapitypes/RIL_3GPP2TONE_ANSWER, RIL_3GPP2TONE_CALLWAITING, RIL_3GPP2TONE_INTERCEPT, RIL_3GPP2TONE_ABRVREORDER, rilapitypes/RIL_3GPP2TONE_MAX, rilapitypes/RIL_3GPP2TONE_CONFIRM, RIL3GPP2TONE, RIL_3GPP2TONE_DIAL, rilapitypes/RIL_3GPP2TONE_ABRVREORDER, RIL3GPP2TONE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_3GPP2TONE_DIAL, rilapitypes/RIL_3GPP2TONE_PIP, RIL_3GPP2TONE_RINGBACK, RIL_3GPP2TONE_REORDER, RIL_3GPP2TONE_BUSY, RIL_3GPP2TONE_ANSWER, rilapitypes/RIL_3GPP2TONE_INTERCEPT, rilapitypes/RIL_3GPP2TONE_BUSY, RIL_3GPP2TONE_ABRVINTERCEPT, rilapitypes/RIL_3GPP2TONE_CALLWAITING, RIL_3GPP2TONE_PIP, rilapitypes/RIL_3GPP2TONE_ABRVINTERCEPT, rilapitypes/RIL_3GPP2TONE_RINGBACK, RIL_3GPP2TONE_MAX, RIL_3GPP2TONE_CONFIRM, rilapitypes/RIL3GPP2TONE
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
-	RIL3GPP2TONE
product: Windows
targetos: Windows
req.typenames: RIL3GPP2TONE
req.product: Windows 10 or later.
---

# RIL3GPP2TONE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RIL3GPP2TONE { 
  RIL_3GPP2TONE_DIAL,
  RIL_3GPP2TONE_RINGBACK,
  RIL_3GPP2TONE_INTERCEPT,
  RIL_3GPP2TONE_ABRVINTERCEPT,
  RIL_3GPP2TONE_REORDER,
  RIL_3GPP2TONE_ABRVREORDER,
  RIL_3GPP2TONE_BUSY,
  RIL_3GPP2TONE_CONFIRM,
  RIL_3GPP2TONE_ANSWER,
  RIL_3GPP2TONE_CALLWAITING,
  RIL_3GPP2TONE_PIP,
  RIL_3GPP2TONE_MAX
} RIL3GPP2TONE;
````


## -enum-fields




### -field RIL_3GPP2TONE_TONEOFF


### -field RIL_3GPP2TONE_DIAL


### -field RIL_3GPP2TONE_RINGBACK


### -field RIL_3GPP2TONE_INTERCEPT


### -field RIL_3GPP2TONE_ABRVINTERCEPT


### -field RIL_3GPP2TONE_REORDER


### -field RIL_3GPP2TONE_ABRVREORDER


### -field RIL_3GPP2TONE_BUSY


### -field RIL_3GPP2TONE_CONFIRM


### -field RIL_3GPP2TONE_ANSWER


### -field RIL_3GPP2TONE_CALLWAITING


### -field RIL_3GPP2TONE_PIP


### -field RIL_3GPP2TONE_MAX

