---
UID: NF:wdm.PoFxQueryCurrentComponentPerfState
title: PoFxQueryCurrentComponentPerfState function (wdm.h)
description: The PoFxQueryCurrentComponentPerfState routine retrieves the active performance state in a component's performance state set.
old-location: kernel\pofxquerycurrentcomponentperfstate.htm
tech.root: kernel
ms.assetid: DFB59020-1F4A-4ABB-8BBE-85F9C8615249
ms.date: 04/30/2018
keywords: ["PoFxQueryCurrentComponentPerfState function"]
ms.keywords: PoFxQueryCurrentComponentPerfState, PoFxQueryCurrentComponentPerfState routine [Kernel-Mode Driver Architecture], kernel.pofxquerycurrentcomponentperfstate, wdm/PoFxQueryCurrentComponentPerfState
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxQueryCurrentComponentPerfState
 - wdm/PoFxQueryCurrentComponentPerfState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PoFxQueryCurrentComponentPerfState
---

# PoFxQueryCurrentComponentPerfState function


## -description

The <b>PoFxQueryCurrentComponentPerfState</b> routine retrieves the active performance state in a component's performance state set.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the device with power management framework (PoFx). The device driver previously received this handle from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param Flags 

[in]
Set to 0. Currently, no flags are defined for this routine.

### -param Component 

[in]
The index that identifies the component whose performance state is being retrieved. This parameter is an index into the <b>Components</b> array in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param SetIndex 

[in]
The index that identifies the performance state set whose performance is being queried. This parameter is an index into the <b>PerfStateSets</b> array in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_info">PO_FX_COMPONENT_PERF_INFO</a> structure that the device driver used to register the component performance states with PoFx. If the <b>PerfStateSets</b> array contains N elements, performance state set indexes range from 0 to N–1.

### -param CurrentPerf 

[in]
A pointer to variable in which the current performance state for the specified performance state set is returned. For more information about the value that is returned, see Remarks.

## -returns

<b>PoFxQueryCurrentComponentPerfState</b> returns <b>STATUS_SUCCESS</b> if the requested operation succeeds. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_INVALID_PARAMETER</b></b></dt>
</dl>
</td>
<td width="60%">
The caller supplied an invalid index for the component or component state set.

</td>
</tr>
</table>

## -remarks

A driver can call the <b>PoFxQueryCurrentComponentPerfState</b> routine to retrieve the current performance state of a given performance state set for a component. If the call succeeds, the <i>CurrentPerf</i> parameter is overwritten with a pointer to a value that specifies the current performance state of the set. This value may be one of the following, depending on the contents of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> structure that the driver passed to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a> routine:

<ul>
<li>For a performance state set that represents a continuous distribution of performance states, this is a value between the <b>Minimum</b> and <b>Maximum</b> members of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> structure.</li>
<li>For a performance state set that represents a discrete number of performance states, this value is an index into the <b>States</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> structure .</li>
</ul>
This call always executes synchronously.

## -see-also

<a href="/windows-hardware/drivers/kernel/component-level-performance-management">Device Performance State Management</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_info">PO_FX_COMPONENT_PERF_INFO</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a>