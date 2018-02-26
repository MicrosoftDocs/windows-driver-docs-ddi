---
UID: NS:pepfx._PEP_COMPONENT_PERF_SET
title: "_PEP_COMPONENT_PERF_SET"
author: windows-driver-content
description: The PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set.
old-location: kernel\pep_component_perf_set.htm
old-project: kernel
ms.assetid: E4EB8052-545C-46AE-A879-1F216B7FD20B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPEP_COMPONENT_PERF_SET, ,, C, E, F, M, N, O, P, PEP_COMPONENT_PERF_SET, PEP_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_SET, PPEP_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], R, S, T, _, _PEP_COMPONENT_PERF_SET, kernel.pep_component_perf_set, pepfx/PEP_COMPONENT_PERF_SET, pepfx/PPEP_COMPONENT_PERF_SET"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_COMPONENT_PERF_SET
product: Windows
targetos: Windows
req.typenames: PEP_COMPONENT_PERF_SET, *PPEP_COMPONENT_PERF_SET
---

# _PEP_COMPONENT_PERF_SET structure


## -description


The <b>PEP_COMPONENT_PERF_SET</b> structure describes the performance states (P-states) in a P-state set.


## -syntax


````
typedef struct _PEP_COMPONENT_PERF_SET {
  UNICODE_STRING      Name;
  ULONGLONG           Flags;
  PEP_PERF_STATE_UNIT Unit;
  PEP_PERF_STATE_TYPE Type;
  union {
    struct {
      ULONG           Count;
      PPEP_PERF_STATE States;
    } Discrete;
    struct {
      ULONGLONG Minimum;
      ULONGLONG Maximum;
    } Range;
  };
} PEP_COMPONENT_PERF_SET, *PPEP_COMPONENT_PERF_SET;
````


## -struct-fields




### -field Name

An optional string that describes the device property controlled by this P-state set.  For example, this string might be "Clock frequency" or "Memory bandwidth". If no such string is available for this P-state, the <b>Name</b> member is set to NULL. Otherwise, this member contains a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the string.


### -field Flags

Set to zero. No flag bits are currently defined for this member.


### -field Unit

A <a href="..\pep_x\ne-pep_x-_pep_perf_state_unit.md">PEP_PERF_STATE_UNIT</a> structure that specifies the units in which the performance values for this P-state set are expressed. Component performance can be expressed in hertz (frequency) or in bits per second (bandwidth).


### -field Type

A <a href="..\pep_x\ne-pep_x-_pep_perf_state_type.md">PEP_PERF_STATE_TYPE</a> enumeration value that indicates the type of performance information that is specified for this component. This member indicates whether the performance values for this P-state set are specified as a list of discrete values or as a continuous range of values.


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

A pointer to an array of <a href="..\pep_x\ns-pep_x-_pep_perf_state.md">PEP_PERF_STATE</a> structures, each of which describes a discrete performance value in this P-state set. The <b>Count</b> member specifies the number of elements in this array. A P-state is identified by its array index. If the array contains N elements, P-state indexes range from 0 to N–1.



#### Range

The range of discrete performance measurement values for this P-state set.



##### Minimum

The minimum value in the range. This value is expressed in the units indicated by the <b>Unit</b> member.



##### Maximum

The maximum value in the range. This value is expressed in the units indicated by the <b>Unit</b> member.


## -remarks



The <b>PerfStateSets</b> member of the <a href="..\pep_x\ns-pep_x-_pep_component_perf_info.md">PEP_COMPONENT_PERF_INFO</a> is the first element in an array of <b>PEP_COMPONENT_PERF_SET</b> structures. All members of the <b>PEP_COMPONENT_PERF_SET</b> structure contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.

Device drivers use the <a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure, which is similar to the <b>PEP_COMPONENT_PERF_SET</b> structure.




## -see-also

<a href="..\pep_x\ne-pep_x-_pep_perf_state_unit.md">PEP_PERF_STATE_UNIT</a>



<a href="..\pep_x\ns-pep_x-_pep_component_perf_info.md">PEP_COMPONENT_PERF_INFO</a>



<a href="..\pep_x\ns-pep_x-_pep_perf_state.md">PEP_PERF_STATE</a>



<a href="..\pep_x\ne-pep_x-_pep_perf_state_type.md">PEP_PERF_STATE_TYPE</a>



<a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COMPONENT_PERF_SET structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

