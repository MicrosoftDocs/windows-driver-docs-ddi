---
UID: NS:hbapiwmi._SM_AddTarget_IN
title: _SM_AddTarget_IN (hbapiwmi.h)
description: The SM_AddTarget_IN structure is used to provide input parameters to the SM_AddTarget WMI method.
old-location: storage\sm_addtarget_in.htm
tech.root: storage
ms.assetid: 02bf5e91-bce0-4b8d-aec6-659ed1efd2b5
ms.date: 03/29/2018
keywords: ["SM_AddTarget_IN structure"]
ms.keywords: "*PSM_AddTarget_IN, PSM_AddTarget_IN, PSM_AddTarget_IN structure pointer [Storage Devices], SM_AddTarget_IN, SM_AddTarget_IN structure [Storage Devices], _SM_AddTarget_IN, hbapiwmi/PSM_AddTarget_IN, hbapiwmi/SM_AddTarget_IN, storage.sm_addtarget_in, structs-Fibre_5be38245-d926-427e-bad7-2d537495eb88.xml"
f1_keywords:
 - "hbapiwmi/SM_AddTarget_IN"
 - "SM_AddTarget_IN"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- hbapiwmi.h
api_name:
- SM_AddTarget_IN
targetos: Windows
req.typenames: SM_AddTarget_IN, *PSM_AddTarget_IN
---

# _SM_AddTarget_IN structure


## -description


The SM_AddTarget_IN structure is used to provide input parameters to the SM_AddTarget WMI method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DiscoveredPortWWN

A worldwide name (WWN) that specifies the discovered target whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field AllTargets

The scope of the target events to report. If this member is zero, the WMI client will receive events that are associated with the port that is indicated by DiscoveredPortWWN. If this member is nonzero, the WMI client will receive events that are associated with all currently discovered targets as well as targets that are discovered in the future.

