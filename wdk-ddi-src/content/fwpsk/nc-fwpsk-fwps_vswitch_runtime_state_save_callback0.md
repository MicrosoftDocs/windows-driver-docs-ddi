---
UID: NC:fwpsk.FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0
title: FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchRuntimeStateSaveNotifyFn (FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0) callout function to notify a callout driver about virtual switch run-time state save events.Note  FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 is a specific version of FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_runtime_state_save_callback0.htm
tech.root: netvista
ms.assetid: 2CDD666F-3D88-4078-9A4C-D7A107806EA7
ms.date: 05/02/2018
ms.keywords: FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0, FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 callback, fwpsk/vSwitchRuntimeStateSaveNotifyFn, netvista.fwps_vswitch_runtime_state_save_callback0, vSwitchRuntimeStateSaveNotifyFn, vSwitchRuntimeStateSaveNotifyFn callback function [Network Drivers Starting with Windows Vista]
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
-	vSwitchRuntimeStateSaveNotifyFn
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 callback function


## -description


The filter engine calls the <i>vSwitchRuntimeStateSaveNotifyFn</i> (<i>FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</i>) callout function to notify a callout driver about virtual switch  run-time state save events.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
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


#### - **runtimeState

The location of the run-time state output result buffer.


### -param *runtimeStateLength [out]

The length, in bytes, of the run-time state information in the run-time state buffer.


#### - runtimeState

The location of the run-time state output result buffer.


## -returns



A callout's 
  
  <i>FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</i> function returns one of the following NTSTATUS codes.

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



A callout driver registers a <i>vSwitchRuntimeStateSaveNotifyFn</i> function  by calling  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>vSwitchRuntimeStateSaveNotifyFn</i> callback is registered, the callout will be notified to retrieve a source VM’s run-time state and to restore a target VM’s run-time state during live migration or a local save and restore operation. In the save case, the <i>eventType</i> parameter of <i>vSwitchRuntimeStateSaveNotifyFn</i> is set to    FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE.

The virtual switch extension protocol driver issues an object identifier (OID) method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598268">OID_SWITCH_NIC_SAVE</a> during an operation to save run-time data for a virtual switch port. The filter driver returns this data so that run-time data for a virtual switch port can be saved and restored at a later time. 

	After the run-time data blob from all callouts are collected, WFP fills the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598216">NDIS_SWITCH_NIC_SAVE_STATE</a> structure with the harvested data and completes the save state request. 

A callout can return STATUS_PENDING from <i>vSwitchRuntimeStateSaveNotifyFn</i>. In this case, WFP will return STATUS_PENDING in the <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> handler and will complete it at a later time. The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation. 

See the <i>vSwitchRuntimeStateRestoreNotifyFn</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh451281">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>) function for information about restoring the run-time state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451281">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598216">NDIS_SWITCH_NIC_SAVE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598268">OID_SWITCH_NIC_SAVE</a>
 

 

