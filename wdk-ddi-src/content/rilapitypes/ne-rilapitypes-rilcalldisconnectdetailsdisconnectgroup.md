---
UID: NE:rilapitypes.RILCALLDISCONNECTDETAILSDISCONNECTGROUP
title: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetailsdisconnectgroup_2.htm
old-project: netvista
ms.assetid: 4d4c87d5-36cd-49ba-8111-cf651f67a451
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLDISCONNECTDETAILSDISCONNECTGROUP, RILCALLDISCONNECTDETAILSDISCONNECTGROUP
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
req.alt-api: RILCALLDISCONNECTDETAILSDISCONNECTGROUP
req.alt-loc: rilapitypes.h
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

### -field RIL_CD_AS_CAUSE


### -field RIL_CD_3GPP_NETWORK_CAUSE


### -field RIL_CD_3GPP2_VENDOR_CAUSE


### -field RIL_CD_OTHER_CAUSE


### -field RIL_CD_3GPP_REJECT_CAUSE


### -field RIL_CD_IMS_SIP_CAUSE


### -field RIL_CD_CAUSE_MAX


## -remarks
