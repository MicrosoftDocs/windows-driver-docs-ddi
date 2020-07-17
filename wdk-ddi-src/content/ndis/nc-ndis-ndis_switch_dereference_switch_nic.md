---
UID: NC:ndis.NDIS_SWITCH_DEREFERENCE_SWITCH_NIC
title: NDIS_SWITCH_DEREFERENCE_SWITCH_NIC (ndis.h)
description: The DereferenceSwitchNic function decrements the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port. The reference counter was incremented through a previous call to ReferenceSwitchNic.
old-location: netvista\DereferenceSwitchNic.htm
tech.root: netvista
ms.assetid: 58C72F81-07B9-45FE-A8BA-0405DBE4CA20
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_DEREFERENCE_SWITCH_NIC callback function"]
ms.keywords: DereferenceSwitchNic, DereferenceSwitchNic callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_DEREFERENCE_SWITCH_NIC, NDIS_SWITCH_DEREFERENCE_SWITCH_NIC callback, ndis/DereferenceSwitchNic, netvista.DereferenceSwitchNic
f1_keywords:
 - "ndis/DereferenceSwitchNic"
 - "DereferenceSwitchNic"
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
- DereferenceSwitchNic
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_DEREFERENCE_SWITCH_NIC callback function


## -description



The <i>DereferenceSwitchNic</i> function decrements the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port. The reference counter was incremented through a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a>.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId [in]

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port  to which the virtual network adapter is connected.


### -param SwitchNicIndex [in]

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the virtual network adapter for which the extensible switch reference counter is to be incremented.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-adapter-index-values">Network Adapter Index Values</a>.


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls <i>DereferenceSwitchNic</i> to decrement the reference counter for a network adapter that is connected to an extensible switch port. While the extensible switch reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a> to delete the connection to the adapter. 

The extension must call <i>DereferenceSwitchNic</i> if it had previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a> for a network adapter connection. 




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_switch_reference_switch_nic">ReferenceSwitchNic</a>
 

 

