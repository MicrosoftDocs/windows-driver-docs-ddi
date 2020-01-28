---
UID: NS:hbapiwmi._SM_GetBindingCapability_OUT
title: _SM_GetBindingCapability_OUT (hbapiwmi.h)
description: The SM_GetBindingCapability_OUT structure is used to receive output parameters from the SM_GetBindingCapability method.
old-location: storage\sm_getbindingcapability_out.htm
tech.root: storage
ms.assetid: 7dfa36be-ab05-478d-b47a-783e599545bf
ms.date: 03/29/2018
ms.keywords: "*PSM_GetBindingCapability_OUT, PSM_GetBindingCapability_OUT, PSM_GetBindingCapability_OUT structure pointer [Storage Devices], SM_GetBindingCapability_OUT, SM_GetBindingCapability_OUT structure [Storage Devices], _SM_GetBindingCapability_OUT, hbapiwmi/PSM_GetBindingCapability_OUT, hbapiwmi/SM_GetBindingCapability_OUT, storage.sm_getbindingcapability_out, structs-Fibre_00260060-51c3-4d04-94a2-bad7903f0e6e.xml"
f1_keywords:
 - "hbapiwmi/SM_GetBindingCapability_OUT"
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
- SM_GetBindingCapability_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_GetBindingCapability_OUT, *PSM_GetBindingCapability_OUT
---

# _SM_GetBindingCapability_OUT structure


## -description


The SM_GetBindingCapability_OUT structure is used to receive output parameters from the SM_GetBindingCapability method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


### -field Flags

The HBA_BIND_CAPABILITY binding capabilities.


## -remarks



The WMI tool suite generates a declaration of the SM_GetBindingCapability_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



