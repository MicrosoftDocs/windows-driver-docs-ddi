---
UID: NE:rilapitypes.RILMSGMWIDETAILLISTPARAMMASK
title: RILMSGMWIDETAILLISTPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwidetaillistparammask_2.htm
old-project: netvista
ms.assetid: 1b0777d4-8977-4dd2-a728-65f0e045efc8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_MWIDETAIL_NUMDETAILITEMS, rilapitypes/RIL_PARAM_MWIDETAIL_NUMDETAILITEMS, rilapitypes/RILMSGMWIDETAILLISTPARAMMASK, rilapitypes/RIL_PARAM_MWIDETAIL_REFNUM, RIL_PARAM_MWIDETAIL_ALL, rilapitypes/RIL_PARAM_MWIDETAIL_DETAILITEMS, RILMSGMWIDETAILLISTPARAMMASK, RILMSGMWIDETAILLISTPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_MWIDETAIL_ALL, RIL_PARAM_MWIDETAIL_REFNUM, RIL_PARAM_MWIDETAIL_DETAILITEMS, netvista.rilmsgmwidetaillistparammask_2
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
-	RILMSGMWIDETAILLISTPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILMSGMWIDETAILLISTPARAMMASK
req.product: Windows 10 or later.
---

# RILMSGMWIDETAILLISTPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMSGMWIDETAILLISTPARAMMASK { 
  RIL_PARAM_MWIDETAIL_REFNUM,
  RIL_PARAM_MWIDETAIL_NUMDETAILITEMS,
  RIL_PARAM_MWIDETAIL_DETAILITEMS,
  RIL_PARAM_MWIDETAIL_ALL
} RILMSGMWIDETAILLISTPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_MWIDETAIL_EXECUTOR


### -field RIL_PARAM_MWIDETAIL_REFNUM


### -field RIL_PARAM_MWIDETAIL_NUMDETAILITEMS


### -field RIL_PARAM_MWIDETAIL_DETAILITEMS


### -field RIL_PARAM_MWIDETAIL_ALL

