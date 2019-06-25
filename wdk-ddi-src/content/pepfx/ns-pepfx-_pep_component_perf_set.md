---
UID: NS:pepfx._PEP_COMPONENT_PERF_SET
title: _PEP_COMPONENT_PERF_SET (pepfx.h)
description: The PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set.
old-location: kernel\pep_component_perf_set.htm
tech.root: kernel
ms.assetid: E4EB8052-545C-46AE-A879-1F216B7FD20B
ms.date: 04/30/2018
ms.keywords: "*PPEP_COMPONENT_PERF_SET, PEP_COMPONENT_PERF_SET, PEP_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_SET, PPEP_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_SET, kernel.pep_component_perf_set, pepfx/PEP_COMPONENT_PERF_SET, pepfx/PPEP_COMPONENT_PERF_SET"
ms.topic: struct
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
- PEP_COMPONENT_PERF_SET
product:
- Windows
targetos: Windows
req.typenames: PEP_COMPONENT_PERF_SET, *PPEP_COMPONENT_PERF_SET
---

# _PEP_COMPONENT_PERF_SET structure


## -description


The <b>PEP_COMPONENT_PERF_SET</b> structure describes the performance states (P-states) in a P-state set.


## -struct-fields




### -field Name

An optional string that describes the device property controlled by this P-state set.  For example, this string might be "Clock frequency" or "Memory bandwidth". If no such string is available for this P-state, the <b>Name</b> member is set to NULL. Otherwise, this member contains a pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the string.


### -field Flags

Set to zero. No flag bits are currently defined for this member.


### -field Unit

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_perf_state_unit">PEP_PERF_STATE_UNIT</a> structure that specifies the units in which the performance values for this P-state set are expressed. Component performance can be expressed in hertz (frequency) or in bits per second (bandwidth).


### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_perf_state_type">PEP_PERF_STATE_TYPE</a> enumeration value that indicates the type of performance information that is specified for this component. This member indicates whether the performance values for this P-state set are specified as a list of discrete values or as a continuous range of values.


### -field Discrete

 


### -field Discrete.Count

 


### -field Discrete.States

 


### -field Range

 


### -field Range.Minimum

 


### -field Range.Maximum

 




#### - ( unnamed union )

A union that contains the performance measurement values for this P-state. This union contains either a list of discrete values (if <b>Type</b> = <b>PepPerfStateTypeDiscrete</b>) or a continuous range of values (if <b>Type</b> = <b>PepPerfStateTypeRange</b>).



#### Discrete

The list of discrete performance values for this P-state set.



##### Count

The number of P-states in this P-state set.



##### States

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_perf_state">PEP_PERF_STATE</a> structures, each of which describes a discrete performance value in this P-state set. The <b>Count</b> member specifies the number of elements in this array. A P-state is identified by its array index. If the array contains N elements, P-state indexes range from 0 to N–1.



#### Range

The range of discrete performance measurement values for this P-state set.



##### Minimum

The minimum value in the range. This value is expressed in the units indicated by the <b>Unit</b> member.



##### Maximum

The maximum value in the range. This value is expressed in the units indicated by the <b>Unit</b> member.


## -remarks



The <b>PerfStateSets</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a> is the first element in an array of <b>PEP_COMPONENT_PERF_SET</b> structures. All members of the <b>PEP_COMPONENT_PERF_SET</b> structure contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.

Device drivers use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> structure, which is similar to the <b>PEP_COMPONENT_PERF_SET</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_perf_state">PEP_PERF_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_perf_state_type">PEP_PERF_STATE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_perf_state_unit">PEP_PERF_STATE_UNIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

