---
UID: NC:ucmmanager.EVT_UCM_CONNECTOR_SET_DATA_ROLE
title: EVT_UCM_CONNECTOR_SET_DATA_ROLE (ucmmanager.h)
description: The client driver's implementation of the EVT_UCM_CONNECTOR_SET_DATA_ROLE event callback function that swaps the data role of the connector to the specified role when attached to a partner connector.
old-location: buses\evt_ucm_connector_set_data_role.htm
tech.root: usbref
ms.assetid: 344E0F3F-7363-4611-AD33-80CCED5D3564
ms.date: 05/07/2018
keywords: ["EVT_UCM_CONNECTOR_SET_DATA_ROLE callback function"]
ms.keywords: EVT_UCM_CONNECTOR_SET_DATA_ROLE, EVT_UCM_CONNECTOR_SET_DATA_ROLE callback, EvtSetDataRole, EvtSetDataRole callback function [Buses], PFN_UCM_CONNECTOR_SET_DATA_ROLE, PFN_UCM_CONNECTOR_SET_DATA_ROLE callback function pointer [Buses], buses.evt_ucm_connector_set_data_role, ucmmanager/EvtSetDataRole
f1_keywords:
 - "ucmmanager/PFN_UCM_CONNECTOR_SET_DATA_ROLE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ucmmanager.h
api_name:
- PFN_UCM_CONNECTOR_SET_DATA_ROLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCM_CONNECTOR_SET_DATA_ROLE callback function


## -description


The client driver's implementation of the <i>EVT_UCM_CONNECTOR_SET_DATA_ROLE</i> event callback function that swaps the data role of the connector to the specified role when attached to a partner connector.  


## -parameters




### -param Connector [in]

Handle to the connector that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a> method.


### -param DataRole [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_partner">UCM_TYPEC_PARTNER</a>-typed flag that specifies the role to set.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To register an <i>EVT_UCM_CONNECTOR_SET_DATA_ROLE</i> callback function, the client driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.  

The USB connector manager framework extension (UcmCx) can request  either <b>UcmTypeCPortStateUfp</b> or   <b>UcmTypeCPortStateDfp</b>. If the port is already in the requested role, the client driver can complete the request without any changes. Otherwise, it starts a data-role swap operation (DR_Swap). The driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectordatadirectionchanged">UcmConnectorDataDirectionChanged</a> to notify UcmCx about the success or failure of that operation. The driver can call that method within the callback function.

The role persists for the current connection.  

If a role-swap operation is pending, UcmCx does not request another role swap. Those operations are serialized across power and data role swaps.

After the swap operation completes, if the partner port sends a DR_Swap request, the client driver must reject the request. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UCM_CONNECTOR_SET_DATA_ROLE     EvtSetDataRole;  

NTSTATUS  
EvtSetDataRole(  
    UCMCONNECTOR  Connector,  
    UCM_TYPE_C_PORT_STATE DataRole  
    )  
{  
    PCONNECTOR_CONTEXT connCtx;  
  
    TRACE_INFO("EvtSetDataRole(%!UCM_TYPE_C_PORT_STATE!) Entry", DataRole);  
  
    connCtx = GetConnectorContext(Connector);

  
    TRACE_FUNC_EXIT();  
    return STATUS_SUCCESS;  
}  
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
 

 

