---
UID: NS:ntddrilapitypes.RILCALLDISCONNECTDETAILS
title: RILCALLDISCONNECTDETAILS (ntddrilapitypes.h)
description: "Microsoft reserves the RILCALLDISCONNECTDETAILS structure for internal use only. Don't use the RILCALLDISCONNECTDETAILS structure in your code."
old-location: netvista\rilcalldisconnectdetails.htm
tech.root: netvista
ms.date: 12/02/2021
keywords: ["RILCALLDISCONNECTDETAILS structure"]
ms.keywords: "*LPRILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS structure [Network Drivers Starting with Windows Vista], netvista.rilcalldisconnectdetails, ntddrilapitypes/RILCALLDISCONNECTDETAILS"
req.header: ntddrilapitypes.h
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
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILS, *LPRILCALLDISCONNECTDETAILS
f1_keywords:
 - RILCALLDISCONNECTDETAILS
 - ntddrilapitypes/RILCALLDISCONNECTDETAILS
 - LPRILCALLDISCONNECTDETAILS
 - ntddrilapitypes/LPRILCALLDISCONNECTDETAILS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddrilapitypes.h
api_name:
 - RILCALLDISCONNECTDETAILS
 - LPRILCALLDISCONNECTDETAILS
---

# RILCALLDISCONNECTDETAILS structure (ntddrilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwDisconnectGroup

### -field causeUnion

### -field RILCAUSEUNION.unGPPCause

Reserved. 

### -field RILCAUSEUNION.unGPPRejectCause

Reserved. 

### -field RILCAUSEUNION.unGPP2Cause

Reserved. 

### -field RILCAUSEUNION.unIMSSIPCause

Reserved. 

### -field RILCAUSEUNION.dwASCode

Reserved. 

### -field RILCAUSEUNION.dwOtherCode

Reserved. 
