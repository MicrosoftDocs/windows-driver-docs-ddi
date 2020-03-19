---
UID: NS:ndis._LOCK_STATE_EX
title: _LOCK_STATE_EX (ndis.h)
description: The LOCK_STATE_EX structure tracks the state of a read/write lock.
old-location: netvista\lock_state_ex.htm
tech.root: netvista
ms.assetid: 558b6fba-a1d8-4255-bca6-e2d83afe9e46
ms.date: 05/02/2018
keywords: ["_LOCK_STATE_EX structure"]
ms.keywords: "*PLOCK_STATE_EX, LOCK_STATE_EX, LOCK_STATE_EX structure [Network Drivers Starting with Windows Vista], PLOCK_STATE_EX, PLOCK_STATE_EX structure pointer [Network Drivers Starting with Windows Vista], _LOCK_STATE_EX, ndis/LOCK_STATE_EX, ndis/PLOCK_STATE_EX, ndis_processor_group_ref_0b6d70d3-0671-49df-977a-c435eb599667.xml, netvista.lock_state_ex"
f1_keywords:
 - "ndis/LOCK_STATE_EX"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- LOCK_STATE_EX
product:
- Windows
targetos: Windows
req.typenames: LOCK_STATE_EX, *PLOCK_STATE_EX
---

# _LOCK_STATE_EX structure


## -description


The <b>LOCK_STATE_EX</b> structure tracks the state of a read/write lock. This structure is opaque to NDIS
   drivers.


## -struct-fields

### -field OldIrql

Reserved.

### -field LockState

Reserved.

### -field Flags

Reserved.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_lock_state">LOCK_STATE</a>
 

 

