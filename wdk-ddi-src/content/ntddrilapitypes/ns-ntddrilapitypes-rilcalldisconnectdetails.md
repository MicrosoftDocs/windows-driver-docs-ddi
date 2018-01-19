---
UID: NS:ntddrilapitypes.RILCALLDISCONNECTDETAILS
title: RILCALLDISCONNECTDETAILS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetails.htm
old-project: netvista
ms.assetid: c933e219-47bb-4896-b5ee-bd2fd59f4e8c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLDISCONNECTDETAILS, *LPRILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLDISCONNECTDETAILS
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
req.typenames: *LPRILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS
---

# RILCALLDISCONNECTDETAILS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCALLDISCONNECTDETAILS {
  RILCALLDISCONNECTDETAILSDISCONNECTGROUP  dwDisconnectGroup;
  NULL                                     RILCAUSEUNION;
  RILCAUSEUNION                            causeUnion;
  RILGPPCAUSE                              unGPPCause;
  RILGPPREJECTCAUSE                        unGPPRejectCause;
  RILGPP2CAUSE                             unGPP2Cause;
  RILIMSSIPCAUSE                           unIMSSIPCause;
  RILCALLDISCONNECTDETAILSASCODE           dwASCode;
  DWORD                                    dwOtherCode;
} RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS;
````


## -struct-fields

### -field dwDisconnectGroup


### -field RILCAUSEUNION


### -field causeUnion


### -field unGPPCause


### -field unGPPRejectCause


### -field unGPP2Cause


### -field unIMSSIPCause


### -field dwASCode


### -field dwOtherCode


## -remarks
