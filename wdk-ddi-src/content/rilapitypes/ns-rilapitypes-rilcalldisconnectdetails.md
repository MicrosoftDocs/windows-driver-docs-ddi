---
UID: NS:rilapitypes.RILCALLDISCONNECTDETAILS
title: RILCALLDISCONNECTDETAILS (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetails.htm
tech.root: netvista
ms.assetid: c933e219-47bb-4896-b5ee-bd2fd59f4e8c
ms.date: 05/02/2018
keywords: ["RILCALLDISCONNECTDETAILS structure"]
ms.keywords: "*LPRILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS structure [Network Drivers Starting with Windows Vista], netvista.rilcalldisconnectdetails, ntddrilapitypes/RILCALLDISCONNECTDETAILS"
f1_keywords:
 - "rilapitypes/RILCALLDISCONNECTDETAILS"
 - "RILCALLDISCONNECTDETAILS"
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddrilapitypes.h
api_name:
- RILCALLDISCONNECTDETAILS
product:
- Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILS, *LPRILCALLDISCONNECTDETAILS
---

# RILCALLDISCONNECTDETAILS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -struct-fields




### -field dwDisconnectGroup


### -field causeUnion


### -field causeUnion.unGPPCause

 


### -field causeUnion.unGPPRejectCause

 


### -field causeUnion.unGPP2Cause

 


### -field causeUnion.unIMSSIPCause

 


### -field causeUnion.dwASCode

 


### -field causeUnion.dwOtherCode

 


### -field RILCAUSEUNION


#### - dwASCode


#### - dwOtherCode


#### - unGPP2Cause


#### - unGPPCause


#### - unGPPRejectCause


#### - unIMSSIPCause

