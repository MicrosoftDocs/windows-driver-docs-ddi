---
UID: NE:rilapitypes.RILCALLDISCONNECTDETAILSASCODE
title: RILCALLDISCONNECTDETAILSASCODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetailsascode_2.htm
old-project: netvista
ms.assetid: 8d5dfc37-682e-41a0-9c61-76ae8f70b154
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_CD_LAYER_MAX, RIL_CD_L2, netvista.rilcalldisconnectdetailsascode_2, RIL_CD_L3, RILCALLDISCONNECTDETAILSASCODE enumeration [Network Drivers Starting with Windows Vista], RIL_CD_LAYER_MAX, rilapitypes/RIL_CD_L3, RILCALLDISCONNECTDETAILSASCODE, rilapitypes/RILCALLDISCONNECTDETAILSASCODE, rilapitypes/RIL_CD_L2
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
-	RILCALLDISCONNECTDETAILSASCODE
product: Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILSASCODE
req.product: Windows 10 or later.
---

# RILCALLDISCONNECTDETAILSASCODE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLDISCONNECTDETAILSASCODE { 
  RIL_CD_L2,
  RIL_CD_L3,
  RIL_CD_LAYER_MAX
} RILCALLDISCONNECTDETAILSASCODE;
````


## -enum-fields




### -field RIL_CD_PHYSICAL_LAYER



### -field RIL_CD_L2



### -field RIL_CD_L3



### -field RIL_CD_LAYER_MAX


