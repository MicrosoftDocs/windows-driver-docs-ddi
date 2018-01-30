---
UID: NE:rilapitypes.RILUICCAPPDATACHANGEENUM
title: RILUICCAPPDATACHANGEENUM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachangeenum_2.htm
old-project: netvista
ms.assetid: 66d5596b-5f5b-46a6-9151-074c4713940f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET, rilapitypes/RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, rilapitypes/RIL_UICCAPP_DATACHANGE_MBDN, rilapitypes/RIL_UICCAPP_DATACHANGE_ESNME, rilapitypes/RILUICCAPPDATACHANGEENUM, RIL_UICCAPP_DATACHANGE_MBDN, RILUICCAPPDATACHANGEENUM enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_UICCAPP_DATACHANGE_MAX, netvista.riluiccappdatachangeenum_2, RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET, RILUICCAPPDATACHANGEENUM, RIL_UICCAPP_DATACHANGE_ESNME, RIL_UICCAPP_DATACHANGE_MAX
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
-	RILUICCAPPDATACHANGEENUM
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGEENUM
req.product: Windows 10 or later.
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


