---
UID: NS:pepfx._PEP_COORDINATED_IDLE_STATE
title: _PEP_COORDINATED_IDLE_STATE (pepfx.h)
description: The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS.
old-location: kernel\pep_coordinated_idle_state.htm
tech.root: kernel
ms.assetid: 0B3B53F8-2D1E-430B-9C51-E35465899811
ms.date: 04/30/2018
keywords: ["_PEP_COORDINATED_IDLE_STATE structure"]
ms.keywords: "*PPEP_COORDINATED_IDLE_STATE, PEP_COORDINATED_IDLE_STATE, PEP_COORDINATED_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_COORDINATED_IDLE_STATE, PPEP_COORDINATED_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_COORDINATED_IDLE_STATE, kernel.pep_coordinated_idle_state, pepfx/PEP_COORDINATED_IDLE_STATE, pepfx/PPEP_COORDINATED_IDLE_STATE"
f1_keywords:
 - "pepfx/PEP_COORDINATED_IDLE_STATE"
 - "PEP_COORDINATED_IDLE_STATE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- pepfx.h
api_name:
- PEP_COORDINATED_IDLE_STATE
targetos: Windows
req.typenames: PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE
---

# _PEP_COORDINATED_IDLE_STATE structure


## -description


The <b>PEP_COORIDNATED_IDLE_STATE</b> structure describes a coordinated idle state to the OS.


## -struct-fields




### -field Latency

The latency of waking from this idle state, in 100ns units.


### -field BreakEvenDuration

Supplies the minimum time the state must be entered to amortize the cost of entering/exiting the state. Idle durations longer than this period should save power when compared to entering a lighter state for the same period.


### -field DependencyCount

Supplies the number of dependencies this coordinated state has on other coordinated states or on processors.


### -field MaximumDependencySize

Supplies the maximum size of a single dependency.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_coordinated_idle_state">PEP_COORDINATED_IDLE_STATE structure</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>
 

 

