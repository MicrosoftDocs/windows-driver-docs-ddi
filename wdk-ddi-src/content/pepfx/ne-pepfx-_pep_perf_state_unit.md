---
UID: NE:pepfx._PEP_PERF_STATE_UNIT
title: _PEP_PERF_STATE_UNIT (pepfx.h)
description: The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.
old-location: kernel\pep_perf_state_unit.htm
tech.root: kernel
ms.assetid: 5E5F049D-4306-4382-B3F7-06C1F5FFE93E
ms.date: 04/30/2018
ms.keywords: "*PPEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT enumeration [Kernel-Mode Driver Architecture], PepPerfStateUnitBandwidth, PepPerfStateUnitFrequency, PepPerfStateUnitMax, PepPerfStateUnitOther, _PEP_PERF_STATE_UNIT, kernel.pep_perf_state_unit, pepfx/PEP_PERF_STATE_UNIT, pepfx/PepPerfStateUnitBandwidth, pepfx/PepPerfStateUnitFrequency, pepfx/PepPerfStateUnitMax, pepfx/PepPerfStateUnitOther"
ms.topic: enum
f1_keywords:
 - "pepfx/PEP_PERF_STATE_UNIT"
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
- PEP_PERF_STATE_UNIT
product:
- Windows
targetos: Windows
req.typenames: PEP_PERF_STATE_UNIT, *PPEP_PERF_STATE_UNIT
---

# _PEP_PERF_STATE_UNIT enumeration


## -description


The <b>PEP_PERF_STATE_UNIT</b> enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.


## -enum-fields




### -field PepPerfStateUnitOther

Some other type of measurement units not explicitly described by this enumeration.


### -field PepPerfStateUnitFrequency

Hertz (frequency units).


### -field PepPerfStateUnitBandwidth

Bits per second (bandwidth units).


### -field PepPerfStateUnitMax

Reserved for use by operating system.


## -remarks



The <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_UNIT</b> enumeration value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>
 

 

