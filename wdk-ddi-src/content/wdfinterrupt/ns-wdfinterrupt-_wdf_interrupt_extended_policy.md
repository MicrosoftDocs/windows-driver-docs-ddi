---
UID: NS:wdfinterrupt._WDF_INTERRUPT_EXTENDED_POLICY
title: _WDF_INTERRUPT_EXTENDED_POLICY (wdfinterrupt.h)
description: The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group.
old-location: wdf\wdf_interrupt_extended_policy.htm
tech.root: wdf
ms.assetid: 28cc79e8-7078-4b29-ab2a-2eeca5c5b8b3
ms.date: 02/26/2018
ms.keywords: "*PWDF_INTERRUPT_EXTENDED_POLICY, DFInterruptObjectRef_db1feccc-0171-4163-b95f-6be057430176.xml, PWDF_INTERRUPT_EXTENDED_POLICY, PWDF_INTERRUPT_EXTENDED_POLICY structure pointer, WDF_INTERRUPT_EXTENDED_POLICY, WDF_INTERRUPT_EXTENDED_POLICY structure, _WDF_INTERRUPT_EXTENDED_POLICY, kmdf.wdf_interrupt_extended_policy, wdf.wdf_interrupt_extended_policy, wdfinterrupt/PWDF_INTERRUPT_EXTENDED_POLICY, wdfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY"
ms.topic: struct
f1_keywords:
 - "wdfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
- wdfinterrupt.h
api_name:
- WDF_INTERRUPT_EXTENDED_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY
---

# _WDF_INTERRUPT_EXTENDED_POLICY structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure contains information about an interrupt's policy, priority, affinity, and group.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Policy

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_policy">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -field Priority

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ne-wdfinterrupt-_wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -field TargetProcessorSetAndGroup

A GROUP_AFFINITY structure that specifies a processor group and a processor affinity mask within the group, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>. The GROUP_AFFINITY structure is defined in <i>Winnt.h</i>. 


## -remarks



The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure is used as input the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetextendedpolicy">WdfInterruptSetExtendedPolicy</a>. 

To initialize a <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_extended_policy_init">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_extended_policy_init">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsetextendedpolicy">WdfInterruptSetExtendedPolicy</a>
 

 

