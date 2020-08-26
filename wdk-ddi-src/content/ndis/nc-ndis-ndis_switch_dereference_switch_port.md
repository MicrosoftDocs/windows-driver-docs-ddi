---
UID: NC:ndis.NDIS_SWITCH_DEREFERENCE_SWITCH_PORT
title: NDIS_SWITCH_DEREFERENCE_SWITCH_PORT (ndis.h)
description: The DereferenceSwitchPort function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to ReferenceSwitchPort.
old-location: netvista\DereferenceSwitchPort.htm
tech.root: netvista
ms.assetid: 976D3A69-C539-4C8E-9664-F85717E5F712
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_DEREFERENCE_SWITCH_PORT callback function"]
ms.keywords: DereferenceSwitchPort, DereferenceSwitchPort callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_DEREFERENCE_SWITCH_PORT, NDIS_SWITCH_DEREFERENCE_SWITCH_PORT callback, ndis/DereferenceSwitchPort, netvista.DereferenceSwitchPort
f1_keywords:
 - "ndis/DereferenceSwitchPort"
 - "DereferenceSwitchPort"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- DereferenceSwitchPort
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_DEREFERENCE_SWITCH_PORT callback function


## -description



The <i>DereferenceSwitchPort</i> function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_port">ReferenceSwitchPort</a>.




## -parameters




### -param NdisSwitchContext 
[in]
An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId 
[in]
An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which the extensible switch reference counter is incremented.


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls <i>DereferenceSwitchPort</i> to decrement the reference counter for an extensible switch port. While the extensible switch reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a> to delete the port.

The extension must call <i>DereferenceSwitchPort</i> if it had previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_port">ReferenceSwitchPort</a> for an extensible switch port. 




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_port">ReferenceSwitchPort</a>
 

 

