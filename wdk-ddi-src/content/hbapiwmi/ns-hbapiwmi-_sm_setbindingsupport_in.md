---
UID: NS:hbapiwmi._SM_SetBindingSupport_IN
title: _SM_SetBindingSupport_IN (hbapiwmi.h)
description: The SM_SetBindingSupport_IN structure is used to provide input parameters to the SM_SetBindingSupport method.
old-location: storage\sm_setbindingsupport_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SetBindingSupport_IN structure"]
ms.keywords: "*PSM_SetBindingSupport_IN, PSM_SetBindingSupport_IN, PSM_SetBindingSupport_IN structure pointer [Storage Devices], SM_SetBindingSupport_IN, SM_SetBindingSupport_IN structure [Storage Devices], _SM_SetBindingSupport_IN, hbapiwmi/PSM_SetBindingSupport_IN, hbapiwmi/SM_SetBindingSupport_IN, storage.sm_setbindingsupport_in, structs-Fibre_9797bfcd-a063-47dd-8a98-0837b3fb7698.xml"
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
targetos: Windows
req.typenames: SM_SetBindingSupport_IN, *PSM_SetBindingSupport_IN
f1_keywords:
 - _SM_SetBindingSupport_IN
 - hbapiwmi/_SM_SetBindingSupport_IN
 - PSM_SetBindingSupport_IN
 - hbapiwmi/PSM_SetBindingSupport_IN
 - SM_SetBindingSupport_IN
 - hbapiwmi/SM_SetBindingSupport_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SM_SetBindingSupport_IN
 - PSM_SetBindingSupport_IN
 - SM_SetBindingSupport_IN
---

# _SM_SetBindingSupport_IN structure


## -description

The SM_SetBindingSupport_IN structure is used to provide input parameters to the SM_SetBindingSupport method.

## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.

### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

### -field Flags

The HBA_BIND_CAPABILITY binding capabilities.

## -remarks

The WMI tool suite generates a declaration of the SM_SetBindingSupport_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SMHBA_BindingEntry WMI class.

