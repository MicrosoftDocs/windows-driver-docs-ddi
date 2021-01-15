---
UID: NS:hbapiwmi._SM_SetBindingSupport_OUT
title: _SM_SetBindingSupport_OUT (hbapiwmi.h)
description: The SM_SetBindingSupport_OUT structure is used to receive output parameters from the SM_SetBindingSupport method.
old-location: storage\sm_setbindingsupport_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SetBindingSupport_OUT structure"]
ms.keywords: "*PSM_SetBindingSupport_OUT, PSM_SetBindingSupport_OUT, PSM_SetBindingSupport_OUT structure pointer [Storage Devices], SM_SetBindingSupport_OUT, SM_SetBindingSupport_OUT structure [Storage Devices], _SM_SetBindingSupport_OUT, hbapiwmi/PSM_SetBindingSupport_OUT, hbapiwmi/SM_SetBindingSupport_OUT, storage.sm_setbindingsupport_out, structs-Fibre_b14ee92a-9c2c-4f8a-be35-b189b0d5e97f.xml"
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
req.typenames: SM_SetBindingSupport_OUT, *PSM_SetBindingSupport_OUT
f1_keywords:
 - _SM_SetBindingSupport_OUT
 - hbapiwmi/_SM_SetBindingSupport_OUT
 - PSM_SetBindingSupport_OUT
 - hbapiwmi/PSM_SetBindingSupport_OUT
 - SM_SetBindingSupport_OUT
 - hbapiwmi/SM_SetBindingSupport_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SM_SetBindingSupport_OUT
 - PSM_SetBindingSupport_OUT
 - SM_SetBindingSupport_OUT
---

# _SM_SetBindingSupport_OUT structure


## -description

The SM_SetBindingSupport_OUT structure is used to receive output parameters from the SM_SetBindingSupport method.

## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SM_SetBindingSupport_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.

