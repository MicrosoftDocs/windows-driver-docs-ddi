---
UID: NC:fwpsk.FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0
title: FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchRuntimeStateRestoreNotifyFn (FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0) callout function to notify a callout driver about virtual switch run-time state restore events.Note  FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0 is a specific version of FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_runtime_state_restore_callback0.htm
old-project: netvista
ms.assetid: E684429C-1BDC-4821-89DF-08FF20D25315
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0, FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0 callback, fwpsk/vSwitchRuntimeStateRestoreNotifyFn, netvista.fwps_vswitch_runtime_state_restore_callback0, vSwitchRuntimeStateRestoreNotifyFn, vSwitchRuntimeStateRestoreNotifyFn callback function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fwpsk.h
api_name:
-	vSwitchRuntimeStateRestoreNotifyFn
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0 callback function


## -description


The filter engine calls the <i>vSwitchRuntimeStateRestoreNotifyFn</i>  (<i>FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</i>) callout function to notify a callout driver about virtual switch run-time state restore events.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param *notifyContext [in, optional]

A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.


### -param *completionContext [in]

A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.




### -param eventType [in]

The type of virtual switch event  specified as one of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.


### -param *vSwitch [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.


<div class="alert"><b>Note</b>  The information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param portId [in]

The source switch port identifier.


### -param *runtimeState

The location of the run-time state output result buffer.


### -param runtimeStateLength [in]

The length, in bytes, of the run-time state information in the run-time state buffer.


## -returns



A callout's 
  
  <i>FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later.  The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



A callout driver registers a <i>vSwitchRuntimeStateRestoreNotifyFn</i> function  by calling  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.

See the <i>vSwitchRuntimeStateSaveNotifyFn</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh451286">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>) function for information about saving the run-time state.

Each saved data segment will be restored with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598267">OID_SWITCH_NIC_RESTORE</a> OID sent through the virtual switch extension stacks on the target system or on the local system during a restore operation. WFP will dispatch the data to the correct callout through <i>vSwitchRuntimeStateRestoreNotifyFn</i> after matching with a registered provider GUID. In this case, the <i>eventType</i> parameter of <i>vSwitchRuntimeStateRestoreNotifyFn</i> is set to    FWPS_VSWITCH_EVENT_RUNTIME_STATE_RESTORE.

A callout can return STATUS_PENDING from <i>vSwitchRuntimeStateRestoreNotifyFn</i>. In this case, WFP will return STATUS_PENDING in the <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> handler and will complete it at a later time. The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451286">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598267">OID_SWITCH_NIC_RESTORE</a>
 

 

