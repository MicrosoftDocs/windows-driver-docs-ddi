---
UID: NS:ndis._LOCK_STATE
title: _LOCK_STATE (ndis.h)
description: The LOCK_STATE structure tracks the state of a read/write lock.
old-location: netvista\lock_state.htm
tech.root: netvista
ms.assetid: d23c7824-b2ab-4316-8d4c-474619a22223
ms.date: 05/02/2018
ms.keywords: "*PLOCK_STATE, LOCK_STATE, LOCK_STATE structure [Network Drivers Starting with Windows Vista], PLOCK_STATE, PLOCK_STATE structure pointer [Network Drivers Starting with Windows Vista], _LOCK_STATE, ndis/LOCK_STATE, ndis/PLOCK_STATE, ndis_processor_group_ref_d04d3375-211e-4ef8-a30b-d2c6b98f9cc1.xml, netvista.lock_state"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use LOCK_STATE_EX instead.
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
- ndis.h
api_name:
- LOCK_STATE
product:
- Windows
targetos: Windows
req.typenames: LOCK_STATE, *PLOCK_STATE
---

# _LOCK_STATE structure


## -description


The <b>LOCK_STATE</b> structure tracks the state of a read/write lock. This structure is opaque to NDIS
   drivers.

## -struct-fields

### -field LockState

Reserved.

### -field OldIrql

Reserved.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_lock_state_ex">LOCK_STATE_EX</a>
 

 

