---
UID: NS:ntifs._VETO_BINDING_ECP_CONTEXT
tech.root: ifsk
title: VETO_BINDING_ECP_CONTEXT
ms.date: 02/09/2024
targetos: Windows
description: Learn more about the VETO_BINDING_ECP_CONTEXT structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: VETO_BINDING_ECP_CONTEXT, *PVETO_BINDING_ECP_CONTEXT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _VETO_BINDING_ECP_CONTEXT
 - PVETO_BINDING_ECP_CONTEXT
 - VETO_BINDING_ECP_CONTEXT
f1_keywords:
 - _VETO_BINDING_ECP_CONTEXT
 - ntifs/_VETO_BINDING_ECP_CONTEXT
 - PVETO_BINDING_ECP_CONTEXT
 - ntifs/PVETO_BINDING_ECP_CONTEXT
 - VETO_BINDING_ECP_CONTEXT
 - ntifs/VETO_BINDING_ECP_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _VETO_BINDING_ECP_CONTEXT
---

## -description

The **VETO_BINDING_ECP_CONTEXT** structure is the ECP context structure associated with [**GUID_ECP_TYPE_VETO_BINDING**](/windows-hardware/drivers/ifs/system-defined-ecps) for vetoing a binding.

## -struct-fields

### -field ShouldVetoBinding

When set true, the binding is vetoed. When set false, the binding is not vetoed.

## -remarks

A filter sitting below *BindFlt* can veto a binding on the system's boot partition only, not any other partition.

For more information, see [Vetoing a binding](/windows-hardware/drivers/ifs/vetoing-a-binding).
