---
UID: NS:ntddndis._NDIS_SWITCH_PARAMETERS
title: "_NDIS_SWITCH_PARAMETERS"
author: windows-driver-content
description: The NDIS_SWITCH_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch.
old-location: netvista\ndis_switch_parameters.htm
old-project: netvista
ms.assetid: 766e042a-3f21-4f57-a780-83f92bef0a6c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_SWITCH_PARAMETERS, ,, A, C, D, E, H, I, M, N, NDIS_SWITCH_PARAMETERS, NDIS_SWITCH_PARAMETERS structure [Network Drivers Starting with Windows Vista], P, PNDIS_SWITCH_PARAMETERS, PNDIS_SWITCH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, W, _, _NDIS_SWITCH_PARAMETERS, netvista.ndis_switch_parameters, ntddndis/NDIS_SWITCH_PARAMETERS, ntddndis/PNDIS_SWITCH_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	ntddndis.h
apiname:
-	NDIS_SWITCH_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PARAMETERS, *PNDIS_SWITCH_PARAMETERS
---

# _NDIS_SWITCH_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PARAMETERS</b> structure contains the configuration data for a Hyper-V extensible switch.


## -syntax


````
typedef struct _NDIS_SWITCH_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_SWITCH_NAME         SwitchName;
  NDIS_SWITCH_FRIENDLYNAME SwitchFriendlyName;
  UINT32                   NumSwitchPorts;
  BOOLEAN                  IsActive;
} NDIS_SWITCH_PARAMETERS, *PNDIS_SWITCH_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field SwitchName

 An <b>NDIS_SWITCH_NAME</b> value that specifies the unique internal name of the extensible switch.

The internal switch name is used by WMI-based policy management applications. For more information, see <a href="https://msdn.microsoft.com/F58A4BC0-C5C6-440D-BEA3-2224F7051BA5">Managing Hyper-V Extensible Switch Policies</a>.


### -field SwitchFriendlyName

 An <b>NDIS_SWITCH_FRIENDLYNAME</b> value that specifies the user-friendly description of the extensible switch.


### -field NumSwitchPorts

A UINT32 value that specifies the number of ports configured on the extensible switch.


### -field IsActive

A BOOLEAN that if TRUE indicates that the Hyper-V extensible switch activation has finished and it is safe to query for other switch configuration such as enumerating ports, NICs, and properties. If FALSE, the extension must wait for the <a href="..\netpnp\ns-netpnp-_net_pnp_event.md">NetEventSwitchActivate</a> PNP event to be issued before querying for switch configuration. 


## -remarks



The <b>NDIS_SWITCH_PARAMETERS</b> structure is used in the 
    OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598270">OID_SWITCH_PARAMETERS</a>.

This structure is also passed in the <i>vSwitch</i> parameter of the following callout functions for Windows Filtering Platform callout drivers:<ul>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_interface_event_callback0.md">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>
</li>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_lifetime_event_callback0.md">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>
</li>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_policy_event_callback0.md">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>
</li>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_port_event_callback0.md">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>
</li>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>
</li>
<li>
<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_save_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>
</li>
</ul>


<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_NAME</b> and  <b>NDIS_SWITCH_FRIENDLYNAME</b> data types are type-defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character.

</div>
<div> </div>



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598270">OID_SWITCH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/44B59154-C5CA-42F0-A972-021833E29D81">_STRING</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_policy_event_callback0.md">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_lifetime_event_callback0.md">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>



<a href="..\netpnp\ns-netpnp-_net_pnp_event.md">NetEventSwitchActivate</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_save_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_interface_event_callback0.md">IF_COUNTEDFWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_port_event_callback0.md">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

