---
UID: NF:wdm.PoFxRegisterComponentPerfStates
title: PoFxRegisterComponentPerfStates function
author: windows-driver-content
description: The PoFxRegisterComponentPerfStates routine registers a device component for performance state management by the power management framework (PoFx).
old-location: kernel\pofxregistercomponentperfstates.htm
old-project: kernel
ms.assetid: 5A52543B-F0EA-4318-A66F-F9FA60FF94F5
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PO_FX_FLAG_PERF_PEP_OPTIONAL, PO_FX_FLAG_PERF_QUERY_ON_ALL_IDLE_STATES, PO_FX_FLAG_PERF_QUERY_ON_F0, PoFxRegisterComponentPerfStates, PoFxRegisterComponentPerfStates routine [Kernel-Mode Driver Architecture], kernel.pofxregistercomponentperfstates, wdm/PoFxRegisterComponentPerfStates
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxRegisterComponentPerfStates
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxRegisterComponentPerfStates function


## -description


The <b>PoFxRegisterComponentPerfStates</b> routine registers a device component for performance state management by the power management framework (PoFx). 


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component whose performance states will be managed. This parameter is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Flags [in]

The flags that modify the behavior of the performance state registration. Set this member to zero or to one of the following flag <b>PO_FX_FLAG_PERF_<i>XXX</i></b> bits:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_PERF_PEP_OPTIONAL"></a><a id="po_fx_flag_perf_pep_optional"></a><dl>
<dt><b>PO_FX_FLAG_PERF_PEP_OPTIONAL</b></dt>
<dt>0x1</dt>
</dl>
</td>
<td width="60%">
Indicates  that the driver can change performance states without assistance from the platform extension plug-in (PEP), or that the driver is registering performance states with PoFx for logging purposes only. If this flag is set, the <b>PoFxRegisterComponentPerfStates</b> call will still succeeded if the PEP does not support performance states for the component.

</td>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_PERF_QUERY_ON_F0"></a><a id="po_fx_flag_perf_query_on_f0"></a><dl>
<dt><b>PO_FX_FLAG_PERF_QUERY_ON_F0</b></dt>
<dt>0x2</dt>
</dl>
</td>
<td width="60%">
For some devices, the PEP may need to a place a performance state set for a component into a certain performance state (known as a <i>nominal performance state</i>) when it idles the component. Drivers set this flag if the component contains nominal performance states, in which case PoFx will query the PEP to determine the current performance state when the component transitions to F0. 

</td>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_PERF_QUERY_ON_ALL_IDLE_STATES"></a><a id="po_fx_flag_perf_query_on_all_idle_states"></a><dl>
<dt><b>PO_FX_FLAG_PERF_QUERY_ON_ALL_IDLE_STATES</b></dt>
<dt>0x4</dt>
</dl>
</td>
<td width="60%">
For some devices, the PEP may need to a place a performance state set for a component into a certain performance state (known as a <i>nominal performance state</i>) when it transitions the component between idle states. Drivers set this flag if this component contains nominal performance states, in which case PoFx will query the PEP to determine the current performance state when the component transitions between idle states.

</td>
</tr>
</table>
 


### -param ComponentPerfStateCallback [in]

A pointer to a  <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine. This routine is called when PoFx has completed logging and notifying the PEP about a performance state transition that is initiated by the driver’s call to <a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a>. This callback may be the same for all components and all devices; PoFx provides the device handle and component index in each completion call.


### -param InputStateInfo [in]

If the driver provides performance state info, this parameter contains a pointer to a driver allocated <a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a> structure that provides performance state information to PoFx. If the driver requires performance state information from the PEP, this parameter must be set to NULL. 


### -param OutputStateInfo [out]

If the driver requires performance state information from the PEP, after a successful registration this parameter contains a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a> structure that provides performance state information defined by the PEP. If the driver provides performance state info, this parameter must be set to NULL. 

The memory allocated for this parameter is managed by PoFx, and the driver should not free this memory when the device is removed. The lifetime of this memory is guaranteed to exceed the lifetime of the PoFx component that contains these performance state sets.


## -returns



<b>PoFxRegisterComponentPerfStates</b> returns <b>STATUS_SUCCESS</b> if PoFx accepts the device's registration of performance states. If any of the necessary information is not provided or incorrect, registration will fail with a return code other than <b>STATUS_SUCCESS</b>. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_NOT_IMPLEMENTED</b></b></dt>
</dl>
</td>
<td width="60%">
The <i>Flags</i> parameter does not include the <b>PO_FX_FLAG_PERF_PEP_OPTIONAL</b> flag and the PEP is not able to provide performance state management for this device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_INVALID_PARAMETER</b></b></dt>
</dl>
</td>
<td width="60%">
Both <i>InputStateInfo</i> and <i>OutputStateInfo</i> are NULL or both of these parameters are not NULL, or there are no performance state sets in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a> structure that was assigned to the <i>InputStateInfo</i> parameter.

</td>
</tr>
</table>
 




## -remarks



Either the driver or the platform extension plug-in (PEP) may provide information about the performance states supported by each component:

<ul>
<li>
If the driver provides performance state information, the driver must set the <i>InputStateInfo</i> parameter to a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a> structure that contains the performance state information. Otherwise, the driver must set this parameter to NULL.

</li>
<li>
If the PEP provides performance state information, the driver must set the <i>OutputStateInfo</i> parameter to a valid pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a> structure that receives the performance state information. Otherwise, the driver must set this parameter to NULL.

</li>
</ul>
If the PEP does not support performance states, the driver may register for performance state support with PoFx for logging purposes only. 

If the driver registers for performance state support for logging purposes only, or if the driver  can function correctly with or without PEP support for performance state management, the driver must set the <b>PO_FX_FLAG_PERF_PEP_OPTIONAL</b> flag in the <i>Flags</i> parameter. If the flag is set, the registration call will succeed even if the PEP does not provide support for performance states.

If the driver requires the PEP to provide performance state information, the driver cannot set the <b>PO_FX_FLAG_PERF_PEP_OPTIONAL</b> flag in the <i>Flags</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a>



<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939832">PO_FX_COMPONENT_PERF_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>
 

 

