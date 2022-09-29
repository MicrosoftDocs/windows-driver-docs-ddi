---
UID: NS:rilapitypes.RILCALLDISCONNECTDETAILS
title: RILCALLDISCONNECTDETAILS (rilapitypes.h)
description: "Don't use this structure in your code. Microsoft reserves the RILCALLDISCONNECTDETAILS structure for internal use only. "
old-location: netvista\rilcalldisconnectdetails.htm
tech.root: netvista
ms.date: 12/10/2021
keywords: ["RILCALLDISCONNECTDETAILS structure"]
ms.keywords: "*LPRILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS structure [Network Drivers Starting with Windows Vista], netvista.rilcalldisconnectdetails, ntddrilapitypes/RILCALLDISCONNECTDETAILS"
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
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILS, *LPRILCALLDISCONNECTDETAILS
f1_keywords:
 - RILCALLDISCONNECTDETAILS
 - rilapitypes/RILCALLDISCONNECTDETAILS
 - LPRILCALLDISCONNECTDETAILS
 - rilapitypes/LPRILCALLDISCONNECTDETAILS
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

# RILCALLDISCONNECTDETAILS structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwDisconnectGroup

### -field causeUnion

### -field RILCAUSEUNION.unGPPCause

### -field RILCAUSEUNION.unGPPRejectCause

### -field RILCAUSEUNION.unGPP2Cause

### -field RILCAUSEUNION.unIMSSIPCause

### -field RILCAUSEUNION.dwASCode

### -field RILCAUSEUNION.dwOtherCode

### -field RILCAUSEUNION



