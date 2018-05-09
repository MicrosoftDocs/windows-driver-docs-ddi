---
UID: NC:fwpsk.FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
title: FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchPolicyEventNotifyFn (FWPS_VSWITCH_POLICY_EVENT_CALLBACK0) callout function to notify the callout driver about virtual switch policy events.Note  FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_POLICY_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_policy_event_callback0.htm
old-project: netvista
ms.assetid: 8D0F61E2-A891-4D51-9E33-BFA491B95505
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FWPS_VSWITCH_POLICY_EVENT_CALLBACK0, FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback, fwpsk/vSwitchPolicyEventNotifyFn, netvista.fwps_vswitch_policy_event_callback0, vSwitchPolicyEventNotifyFn, vSwitchPolicyEventNotifyFn callback function [Network Drivers Starting with Windows Vista]
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
-	vSwitchPolicyEventNotifyFn
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback function


## -description


The filter engine calls the 
  
  <i>vSwitchPolicyEventNotifyFn</i> (<i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i>) callout function to notify the callout driver about virtual switch policy events.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
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

### -param *vSwitchPortProperty [in, optional]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure. The virtual switch port property.


### -param *vSwitchPortPropertyDelete [in, optional]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure. The virtual switch port property.


## -returns



A callout's 
  
  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.

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



A callout driver registers a 
  
  <i>vSwitchPolicyEventNotifyFn</i> function  by calling  
    
    the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>vSwitchPolicyEventNotifyFn</i> callback is registered, the callout on the target host will be notified about the policy configured for the virtual switch port during live migration and before the migrating VM can run on the new host. 

Without live migration, <i>vSwitchPolicyEventNotifyFn</i> will also be invoked for a VM save operation. 

Changes to vendor filtering policies that are configured through the VMMS WMI interface are passed to the WFP virtual switch extension with OID requests.  These OIDs carry a <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure with the <b>PropertyType</b> member set to the  <b>NdisSwitchPortPropertyTypeCustom</b> type.

The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_ADD type set in the <i>eventType</i> parameter  to notify  callout drivers about the addition of a policy property for a virtual switch port.


The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_UPDATE type set in the <i>eventType</i> parameter   to notify callout filter drivers about the update of a property for a virtual switch port policy.


These OIDs also include a property identifier GUID that uniquely identifies which WFP provider the policy belongs to. The property identifier GUID is provided when an vendor  configures its policy through VMMS, and the GUID must be the same GUID the vendor uses to register its provider with WFP.

WFP attempts to match the property identifier GUID with the provider GUID specified from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a> function. If there is a match, WFP invokes the corresponding <i>vSwitchPolicyEventNotifyFn</i> and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure to the callout.

The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_DELETE type set in the <i>eventType</i> parameter  to notify callout filter drivers about the deletion of a policy property for a virtual switch port. The delete properties are specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure.


If the callout returns STATUS_PENDING from <i>vSwitchPolicyEventNotifyFn</i>, WFP returns STATUS_PENDING to the <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> handler.   The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

