---
UID: NS:hbapiwmi._SM_SetPersistentBinding_IN
title: _SM_SetPersistentBinding_IN (hbapiwmi.h)
description: The SM_SetPersistentBinding_IN structure is used to provide input parameters to the SM_SetPersistentBinding method.
old-location: storage\sm_setpersistentbinding_in.htm
tech.root: storage
ms.assetid: 33a8c609-aa65-4629-b4ee-3723e614d400
ms.date: 03/29/2018
keywords: ["_SM_SetPersistentBinding_IN structure"]
ms.keywords: "*PSM_SetPersistentBinding_IN, PSM_SetPersistentBinding_IN, PSM_SetPersistentBinding_IN structure pointer [Storage Devices], SM_SetPersistentBinding_IN, SM_SetPersistentBinding_IN structure [Storage Devices], _SM_SetPersistentBinding_IN, hbapiwmi/PSM_SetPersistentBinding_IN, hbapiwmi/SM_SetPersistentBinding_IN, storage.sm_setpersistentbinding_in, structs-Fibre_9af25c8f-f9de-482d-8103-f372405d7771.xml"
f1_keywords:
 - "hbapiwmi/SM_SetPersistentBinding_IN"
 - "SM_SetPersistentBinding_IN"
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
- SM_SetPersistentBinding_IN
targetos: Windows
req.typenames: SM_SetPersistentBinding_IN, *PSM_SetPersistentBinding_IN
---

# _SM_SetPersistentBinding_IN structure


## -description


The SM_SetPersistentBinding_IN structure is used to provide input parameters to the SM_SetPersistentBinding method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


### -field Entry

A list of MS_SMHBA_BINDINGENTRY types for persistent binding.


## -remarks



The WMI tool suite generates a declaration of the SM_SetPersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



