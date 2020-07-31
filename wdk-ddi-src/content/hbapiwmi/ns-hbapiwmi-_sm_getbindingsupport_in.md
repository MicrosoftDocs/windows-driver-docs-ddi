---
UID: NS:hbapiwmi._SM_GetBindingSupport_IN
title: _SM_GetBindingSupport_IN (hbapiwmi.h)
description: The SM_GetBindingSupport_IN structure is used to provide input parameters to the SM_GetBindingSupport method.
old-location: storage\sm_getbindingsupport_in.htm
tech.root: storage
ms.assetid: c89d86fe-fe8c-48d2-a5c2-7971ea96b7ad
ms.date: 03/29/2018
keywords: ["_SM_GetBindingSupport_IN structure"]
ms.keywords: "*PSM_GetBindingSupport_IN, PSM_GetBindingSupport_IN, PSM_GetBindingSupport_IN structure pointer [Storage Devices], SM_GetBindingSupport_IN, SM_GetBindingSupport_IN structure [Storage Devices], _SM_GetBindingSupport_IN, hbapiwmi/PSM_GetBindingSupport_IN, hbapiwmi/SM_GetBindingSupport_IN, storage.sm_getbindingsupport_in, structs-Fibre_f13c3a99-7626-4dda-b0f2-8505b7aff3b5.xml"
f1_keywords:
 - "hbapiwmi/SM_GetBindingSupport_IN"
 - "SM_GetBindingSupport_IN"
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
- SM_GetBindingSupport_IN
targetos: Windows
req.typenames: SM_GetBindingSupport_IN, *PSM_GetBindingSupport_IN
---

# _SM_GetBindingSupport_IN structure


## -description


The SM_GetBindingSupport_IN structure is used to provide input parameters to the SM_GetBindingSupport method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


## -remarks



The WMI tool suite generates a declaration of the SM_GetBindingSupport_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SMHBA_BindingEntry WMI class.



