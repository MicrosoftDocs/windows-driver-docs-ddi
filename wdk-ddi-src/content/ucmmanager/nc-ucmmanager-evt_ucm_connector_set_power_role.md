---
UID: NC:ucmmanager.EVT_UCM_CONNECTOR_SET_POWER_ROLE
title: EVT_UCM_CONNECTOR_SET_POWER_ROLE (ucmmanager.h)
description: The client driver's implementation of the EVT_UCM_CONNECTOR_SET_POWER_ROLE event callback function that sets the power role of the connector to the specified role when attached to a partner connector.
old-location: buses\evt_ucm_connector_set_power_role.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCM_CONNECTOR_SET_POWER_ROLE callback function"]
ms.keywords: EVT_UCM_CONNECTOR_SET_POWER_ROLE, EVT_UCM_CONNECTOR_SET_POWER_ROLE callback, EvtSetDataRole, EvtSetDataRole callback function [Buses], PFN_UCM_CONNECTOR_SET_POWER_ROLE, PFN_UCM_CONNECTOR_SET_POWER_ROLE callback function pointer [Buses], buses.evt_ucm_connector_set_power_role, ucmmanager/EvtSetDataRole
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCM_CONNECTOR_SET_POWER_ROLE
 - ucmmanager/EVT_UCM_CONNECTOR_SET_POWER_ROLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ucmmanager.h
api_name:
 - EVT_UCM_CONNECTOR_SET_POWER_ROLE
---

# EVT_UCM_CONNECTOR_SET_POWER_ROLE callback function


## -description

The client driver's implementation of the <i>EVT_UCM_CONNECTOR_SET_POWER_ROLE</i> event callback function that sets the power  role of the connector to the specified role when attached to a partner connector.

## -parameters

### -param Connector [in]


Handle to the connector that the client driver received in a previous call to  the <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a> method.

### -param PowerRole [in]


A <a href="/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_power_role">UCM_POWER_ROLE</a>-typed flag that specifies the role to set.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

To register an <i>EVT_UCM_CONNECTOR_SET_POWER_ROLE</i> callback function, the client must call <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.

The USB connector manager framework extension (UcmCx) can request either <b>UcmPowerRoleSink</b> or  <b>UcmPowerRoleSource</b>. If the port is already in the requested role, the client driver can complete the request without any changes. Otherwise, it starts a power-role swap operation (PR_Swap). The driver calls <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorpowerdirectionchanged">UcmConnectorPowerDirectionChanged</a> to notify UcmCx about the success or failure of that operation. 
The driver can call that method within the callback function.

The role persists for the current connection.  

If a role-swap operation is pending, UcmCx does not request another role swap. Those operations are serialized across power and data role swaps.

After the swap operation completes, if the partner port sends a PR_Swap request, the client driver must reject the request. 


#### Examples


```

EVT_UCM_CONNECTOR_SET_POWER_ROLE     EvtSetPowerRole;  

NTSTATUS  
EvtSetPowerRole(  
    UCMCONNECTOR Connector,  
    UCM_POWER_ROLE PowerRole  
    )  
{  
    PCONNECTOR_CONTEXT connCtx;  
  
    TRACE_INFO("EvtSetPowerRole(%!UCM_POWER_ROLE!) Entry", PowerRole);  
  
    connCtx = GetConnectorContext(Connector);  

    //PR_Swap operation.  
  
  
    TRACE_FUNC_EXIT();  
    return STATUS_SUCCESS;  
}  

```

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>

