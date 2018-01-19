---
UID: NE:ntddrilapitypes.RILUICCAPPDATACHANGEENUM
title: RILUICCAPPDATACHANGEENUM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachangeenum.htm
old-project: netvista
ms.assetid: 6960080f-03dc-4c5f-8cd8-b96d030f2bd3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCAPPDATACHANGEENUM, RILUICCAPPDATACHANGEENUM
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
req.alt-api: RILUICCAPPDATACHANGEENUM
req.alt-loc: ntddrilapitypes.h
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

### -field RIL_UICCAPP_DATACHANGE_MBDN


### -field RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_UNSET


### -field RIL_UICCAPP_DATACHANGE_EF_CSP_PLMN_SET


### -field RIL_UICCAPP_DATACHANGE_ESNME


### -field RIL_UICCAPP_DATACHANGE_MAX


## -remarks
