---
UID: NS:hbapiwmi._SM_GetPersistentBinding_IN
title: _SM_GetPersistentBinding_IN (hbapiwmi.h)
description: The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.
old-location: storage\sm_getpersistentbinding_in.htm
tech.root: storage
ms.assetid: 6c716394-1e82-40d2-befc-50a0ea88f750
ms.date: 03/29/2018
keywords: ["SM_GetPersistentBinding_IN structure"]
ms.keywords: "*PSM_GetPersistentBinding_IN, PSM_GetPersistentBinding_IN, PSM_GetPersistentBinding_IN structure pointer [Storage Devices], SM_GetPersistentBinding_IN, SM_GetPersistentBinding_IN structure [Storage Devices], _SM_GetPersistentBinding_IN, hbapiwmi/PSM_GetPersistentBinding_IN, hbapiwmi/SM_GetPersistentBinding_IN, storage.sm_getpersistentbinding_in, structs-Fibre_2cf97173-2aa3-4770-865a-825f5db0daf1.xml"
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
req.typenames: SM_GetPersistentBinding_IN, *PSM_GetPersistentBinding_IN
f1_keywords:
 - _SM_GetPersistentBinding_IN
 - hbapiwmi/_SM_GetPersistentBinding_IN
 - PSM_GetPersistentBinding_IN
 - hbapiwmi/PSM_GetPersistentBinding_IN
 - SM_GetPersistentBinding_IN
 - hbapiwmi/SM_GetPersistentBinding_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_GetPersistentBinding_IN
---

# _SM_GetPersistentBinding_IN structure


## -description

The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.

## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.

### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

### -field InEntryCount

The number of persistent bindings that are associated with the HBA.

## -remarks

The WMI tool suite generates a declaration of the SM_GetPersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

