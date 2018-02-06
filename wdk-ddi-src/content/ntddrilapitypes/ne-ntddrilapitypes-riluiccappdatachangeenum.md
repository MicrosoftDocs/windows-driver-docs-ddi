---
UID: NE:ntddrilapitypes.RILUICCAPPDATACHANGEENUM
title: RILUICCAPPDATACHANGEENUM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachangeenum.htm
old-project: netvista
ms.assetid: 6960080f-03dc-4c5f-8cd8-b96d030f2bd3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, RIL_UICCAPP_DATACHANGE_ESNME, ntddrilapitypes/RILUICCAPPDATACHANGEENUM, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_MBDN, RILUICCAPPDATACHANGEENUM enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_UICCAPP_DATACHANGE_ESNME, RIL_UICCAPP_DATACHANGE_MBDN, RIL_UICCAPP_DATACHANGE_MAX, ntddrilapitypes/RIL_UICCAPP_DATACHANGE_MAX, RILUICCAPPDATACHANGEENUM, netvista.riluiccappdatachangeenum, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET
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
-	RILUICCAPPDATACHANGEENUM
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGEENUM
---

# RILUICCAPPDATACHANGEENUM enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILUICCAPPDATACHANGEENUM { 
  RIL_UICCAPP_DATACHANGE_MBDN,
  RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET,
  RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET,
  RIL_UICCAPP_DATACHANGE_ESNME,
  RIL_UICCAPP_DATACHANGE_MAX
} RILUICCAPPDATACHANGEENUM;
````


## -enum-fields




### -field RIL_UICCAPP_DATACHANGE_MSISDN



### -field RIL_UICCAPP_DATACHANGE_MBDN



### -field RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET



### -field RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET



### -field RIL_UICCAPP_DATACHANGE_ESNME



### -field RIL_UICCAPP_DATACHANGE_MAX


