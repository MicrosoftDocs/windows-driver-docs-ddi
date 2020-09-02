---
UID: NC:ndis.NDIS_SWITCH_REFERENCE_SWITCH_NIC
title: NDIS_SWITCH_REFERENCE_SWITCH_NIC (ndis.h)
description: The ReferenceSwitchNic function increments the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port.
old-location: netvista\ReferenceSwitchNic.htm
tech.root: netvista
ms.assetid: 8F4C76FA-A386-4A3D-8C9F-3CFF69382702
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_REFERENCE_SWITCH_NIC callback function"]
ms.keywords: NDIS_SWITCH_REFERENCE_SWITCH_NIC, NDIS_SWITCH_REFERENCE_SWITCH_NIC callback, ReferenceSwitchNic, ReferenceSwitchNic callback function [Network Drivers Starting with Windows Vista], ndis/ReferenceSwitchNic, netvista.ReferenceSwitchNic
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_SWITCH_REFERENCE_SWITCH_NIC
 - ndis/NDIS_SWITCH_REFERENCE_SWITCH_NIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ReferenceSwitchNic
---

# NDIS_SWITCH_REFERENCE_SWITCH_NIC callback function


## -description

The <i>ReferenceSwitchNic</i> function increments the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port.

## -parameters

### -param NdisSwitchContext 

[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the  extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param SwitchPortId 

[in]
An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port  to which the virtual network adapter is connected.

### -param SwitchNicIndex 

[in]
An NDIS_SWITCH_NIC_INDEX value that specifies the index of the virtual network adapter for which the extensible switch reference counter is to be incremented.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-adapter-index-values">Network Adapter Index Values</a>.

<div class="alert"><b>Note</b>  This parameter must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

## -returns

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## -remarks

The extensible switch extension calls <i>ReferenceSwitchNic</i> to increment a reference counter for a network adapter that is connected to an extensible switch port. While the reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a> to delete the connection to the adapter. 

After the extension calls <i>ReferenceSwitchNic</i>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_nic">DereferenceSwitchNic</a> to decrement the extensible switch reference counter. 

The extension  should call <i>ReferenceSwitchNic</i> before it performs the following operations:

<ul>
<li>
Forwards an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-request">OID_SWITCH_NIC_REQUEST</a> OID request over the extensible switch control path to an underlying physical network adapter. 


For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-oid-requests-to-physical-network-adapters">Managing OID Requests to Physical Network Adapters</a>.

</li>
<li>
Forwards an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-switch-nic-status">NDIS_STATUS_SWITCH_NIC_STATUS</a> status indication over the extensible switch control path from an underlying external adapter.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-ndis-status-indications-from-physical-network-adapters">Managing NDIS Status Indications from Physical Network Adapters</a>.

</li>
</ul>
<div class="alert"><b>Note</b>  The extension must not call <i>ReferenceSwitchNic</i> when forwarding packets over the extensible switch data path. The extensible switch interface manages its own reference counters for packets that are forwarded to ports and network adapter connections over the data path.</div>
<div> </div>
The extension calls <i>ReferenceSwitchNic</i> after the network adapter connection has reached the <i>Network adapter connection created</i> state. The extension must not call <i>ReferenceSwitchNic</i> after the connection has reached the <i>Network adapter disconnected</i> or <i>Network adapter deleted</i> states. For more information about these states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.

<div class="alert"><b>Note</b>  When the extension calls <i>ReferenceSwitchNic</i>, it does not have to synchronize the call with its code that handles OID requests. As a result, it is possible for the extension to call <i>ReferenceSwitchNic</i> while the protocol edge of the extensible switch issues an OID request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-disconnect">OID_SWITCH_NIC_DISCONNECT</a>. However, if the call to <i>ReferenceSwitchNic</i> completes with NDIS_STATUS_SUCCESS, the extension can still forward <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-request">OID_SWITCH_NIC_REQUEST</a> OID request or <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-switch-nic-status">NDIS_STATUS_SWITCH_NIC_STATUS</a> status indications after it handles the OID_SWITCH_NIC_DISCONNECT OID request.</div>
<div> </div>

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_nic">DereferenceSwitchNic</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-switch-nic-status">NDIS_STATUS_SWITCH_NIC_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-disconnect">OID_SWITCH_NIC_DISCONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-request">OID_SWITCH_NIC_REQUEST</a>

