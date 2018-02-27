---
UID: NE:rilapitypes.RILCALLDISCONNECTDETAILSDISCONNECTGROUP
title: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetailsdisconnectgroup_2.htm
old-project: netvista
ms.assetid: 4d4c87d5-36cd-49ba-8111-cf651f67a451
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLDISCONNECTDETAILSDISCONNECTGROUP, RILCALLDISCONNECTDETAILSDISCONNECTGROUP enumeration [Network Drivers Starting with Windows Vista], RIL_CD_3GPP2_VENDOR_CAUSE, RIL_CD_3GPP_NETWORK_CAUSE, RIL_CD_3GPP_REJECT_CAUSE, RIL_CD_AS_CAUSE, RIL_CD_CAUSE_MAX, RIL_CD_IMS_SIP_CAUSE, RIL_CD_OTHER_CAUSE, netvista.rilcalldisconnectdetailsdisconnectgroup_2, rilapitypes/RILCALLDISCONNECTDETAILSDISCONNECTGROUP, rilapitypes/RIL_CD_3GPP2_VENDOR_CAUSE, rilapitypes/RIL_CD_3GPP_NETWORK_CAUSE, rilapitypes/RIL_CD_3GPP_REJECT_CAUSE, rilapitypes/RIL_CD_AS_CAUSE, rilapitypes/RIL_CD_CAUSE_MAX, rilapitypes/RIL_CD_IMS_SIP_CAUSE, rilapitypes/RIL_CD_OTHER_CAUSE
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
-	RILCALLDISCONNECTDETAILSDISCONNECTGROUP
product: Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
req.product: Windows 10 or later.
---

# RILCALLDISCONNECTDETAILSDISCONNECTGROUP enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLDISCONNECTDETAILSDISCONNECTGROUP { 
  RIL_CD_AS_CAUSE,
  RIL_CD_3GPP_NETWORK_CAUSE,
  RIL_CD_3GPP2_VENDOR_CAUSE,
  RIL_CD_OTHER_CAUSE,
  RIL_CD_3GPP_REJECT_CAUSE,
  RIL_CD_IMS_SIP_CAUSE,
  RIL_CD_CAUSE_MAX
} RILCALLDISCONNECTDETAILSDISCONNECTGROUP;
````


## -enum-fields




### -field RIL_CD_UNKNOWN_CAUSE


### -field RIL_CD_AS_CAUSE


### -field RIL_CD_3GPP_NETWORK_CAUSE


### -field RIL_CD_3GPP2_VENDOR_CAUSE


### -field RIL_CD_OTHER_CAUSE


### -field RIL_CD_3GPP_REJECT_CAUSE


### -field RIL_CD_IMS_SIP_CAUSE


### -field RIL_CD_CAUSE_MAX

