---
UID: NC:ndis.NDIS_SWITCH_REFERENCE_SWITCH_PORT
title: NDIS_SWITCH_REFERENCE_SWITCH_PORT (ndis.h)
description: The ReferenceSwitchPort function increments the Hyper-V extensible switch reference counter for an extensible switch port.
old-location: netvista\ReferenceSwitchPort.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_REFERENCE_SWITCH_PORT callback function"]
ms.keywords: NDIS_SWITCH_REFERENCE_SWITCH_PORT, NDIS_SWITCH_REFERENCE_SWITCH_PORT callback, ReferenceSwitchPort, ReferenceSwitchPort callback function [Network Drivers Starting with Windows Vista], ndis/ReferenceSwitchPort, netvista.ReferenceSwitchPort
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
 - NDIS_SWITCH_REFERENCE_SWITCH_PORT
 - ndis/NDIS_SWITCH_REFERENCE_SWITCH_PORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - NDIS_SWITCH_REFERENCE_SWITCH_PORT
---

# NDIS_SWITCH_REFERENCE_SWITCH_PORT callback function


## -description

The <i>ReferenceSwitchPort</i> function increments the Hyper-V extensible switch reference counter for an extensible switch port.

## -parameters

### -param NdisSwitchContext 

[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param SwitchPortId 

[in]
An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which the extensible switch reference counter is incremented.

<div class="alert"><b>Note</b>  The <i>SwitchPortId</i> parameter must specify the identifier of a port that is in a created state. Identifiers for ports that are in a teardown or deleted state cannot be specified. For more information about port states, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

## -returns

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## -remarks

The extensible switch extension calls <i>ReferenceSwitchPort</i> to increment the reference counter for an extensible switch port. While the reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a> to delete the extensible switch port. 

After the extension calls <i>ReferenceSwitchPort</i>, it must call <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_port">DereferenceSwitchPort</a> to decrement the reference counter.

The extension calls <i>ReferenceSwitchPort</i> after the port has reached the <i>Port created</i> state. The extension must not call <i>ReferenceSwitchPort</i> after the connection has reached the <i>Port tearing down</i> or <i>Port not created</i> states. For more information about these states, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.

 The extension must call <i>ReferenceSwitchPort</i> when it performs any operation that requires the port to be in an active state. For example, the extension must  call <i>ReferenceSwitchPort</i> before it issues an OID method request of <a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a>.

The extension calls <i>ReferenceSwitchPort</i> after the port has reached the <i>Port created</i> state. The extension must not call <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a> after the port has reached the <i>Port tearing down</i> state. For more information about these states, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-port-and-network-adapter-states">Hyper-V Extensible Switch Port and Network Adapter States</a>.

<div class="alert"><b>Note</b>  When the extension calls <i>ReferenceSwitchPort</i>, it does not have to synchronize the call with its code that handles OID requests. As a result, it is possible for the extension to call <i>ReferenceSwitchPort</i> while the protocol edge of the extensible switch issues an OID request of <a href="/windows-hardware/drivers/network/oid-switch-port-teardown">OID_SWITCH_PORT_TEARDOWN</a>. However, if the call to <i>ReferenceSwitchPort</i> completes with NDIS_STATUS_SUCCESS, the extension can still issue the <a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a> OID request after it handles the OID_SWITCH_PORT_TEARDOWN OID request.</div>
<div> </div>

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_dereference_switch_nic">DereferenceSwitchNic</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a>



<a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a>



<a href="/windows-hardware/drivers/network/oid-switch-port-teardown">OID_SWITCH_PORT_TEARDOWN</a>

