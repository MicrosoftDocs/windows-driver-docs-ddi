---
UID: NC:fwpsk.FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0
title: FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchLifetimeNotifyFn (FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0) callout function to notify the callout driver about create and delete events for a virtual switch.Note  FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_lifetime_event_callback0.htm
old-project: netvista
ms.assetid: 6A2058FB-AE3D-48F0-B1D9-3B8894A5419E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0, fwpsk/vSwitchLifetimeNotifyFn, netvista.fwps_vswitch_lifetime_event_callback0, vSwitchLifetimeNotifyFn, vSwitchLifetimeNotifyFn callback function [Network Drivers Starting with Windows Vista]
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
-	vSwitchLifetimeNotifyFn
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0 callback


## -description


The filter engine calls the  
  
  <i>vSwitchLifetimeNotifyFn</i> (<i>FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</i>) callout function to notify the callout driver about create and delete events
  for  a virtual switch.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -prototype


````
FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0 vSwitchLifetimeNotifyFn;

NTSTATUS NTAPI vSwitchLifetimeNotifyFn(
  _In_opt_       void                    *notifyContext,
  _In_           FWPS_VSWITCH_EVENT_TYPE eventType,
  _In_     const  NDIS_SWITCH_PARAMETERS *vSwitch,
  _In_opt_ const NDIS_SWITCH_PORT_ARRAY  *vSwitchPorts,
  _In_opt_ const NDIS_SWITCH_NIC_ARRAY   *vSwitchInterfaces
)
{ ... }
````


## -parameters




### -param *notifyContext [in, optional]

A pointer to a context supplied by the callout driver. The driver passed this pointer to the  <i>notifyContext</i> parameter of the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.


### -param eventType [in]

The type of virtual switch event  specified as one of the <a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.


### -param *vSwitch [in]

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.


<div class="alert"><b>Note</b>  The information in the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param *vSwitchPorts [in, optional]

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_array.md">NDIS_SWITCH_PORT_ARRAY</a> structure that specifies an array of port configuration parameters. Each element in the array specifies the parameters for a port on a virtual switch.   



### -param *vSwitchInterfaces [in, optional]

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_array.md">NDIS_SWITCH_NIC_ARRAY</a> structure that specifies an array of miniport adapter configuration parameters. Each element in the array specifies the parameters for a virtual or physical miniport adapter that is attached to a port on a virtual switch.   



## -returns



A callout's 
  
  <i>FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.

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
  
  <i>vSwitchLifetimeNotifyFn</i> callback function  by calling  
    
    the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
 function.
   

If the <i>vSwitchLifetimeNotifyFn</i> callback is registered, the WFP filter driver notifies the callout driver when a  virtual switch instance is created. Multiple instances of a virtual switch can be present  in a Hyper-V host at the same time.

The WFP filter driver queries the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598270">OID_SWITCH_PARAMETERS</a> OID in the <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function to obtain the virtual switch identifier that is  associated with the current instance of the virtual switch. The WFP filter driver also queries the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598261">OID_SWITCH_NIC_ARRAY</a> and   <a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a> OIDs to obtain the initial set of configured virtual NICs and virtual ports. The WFP filter driver passes  the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_array.md">NDIS_SWITCH_PORT_ARRAY</a> and <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_array.md">NDIS_SWITCH_NIC_ARRAY</a> structure information from the OIDs to  <i>vSwitchLifetimeNotifyFn</i> with FWPS_VSWITCH_EVENT_VSWITCH_CREATE set in the <i>eventType</i> parameter. 


In the WFP filter driver's  <a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>, the filter calls  with FWPS_VSWITCH_EVENT_VSWITCH_DELETE set in the <i>eventType</i><i>vSwitchLifetimeNotifyFn</i> parameter.

A callout driver cannot return STATUS_PENDING from <i>vSwitchLifetimeNotifyFn</i>.




## -see-also

<a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598270">OID_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598261">OID_SWITCH_NIC_ARRAY</a>



<a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>



<a href="..\ndis\nf-ndis-ndisfrestartcomplete.md">NdisFRestartComplete</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_array.md">NDIS_SWITCH_NIC_ARRAY</a>



<a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_array.md">NDIS_SWITCH_PORT_ARRAY</a>



<a href="..\fwpsk\nf-fwpsk-fwpsvswitchnotifycomplete0.md">FwpsvSwitchNotifyComplete0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_port_event_callback0.md">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0 callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

