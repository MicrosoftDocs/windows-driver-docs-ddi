---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_GET_20PORT_INFO
title: EVT_UCX_ROOTHUB_GET_20PORT_INFO (ucxroothub.h)
description: The client driver's implementation that UCX calls when it receives a request for information about USB 2.0 ports on the root hub.
old-location: buses\evt_ucx_roothub_get_20port_info.htm
tech.root: usbref
ms.assetid: c4a328fb-ffbf-4da4-b52d-6cea58e56b5e
ms.date: 05/07/2018
keywords: ["EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function"]
ms.keywords: EVT_UCX_ROOTHUB_GET_20PORT_INFO, EVT_UCX_ROOTHUB_GET_20PORT_INFO callback, EvtUcxRootHubGet20PortInfo, EvtUcxRootHubGet20PortInfo callback function [Buses], PEVT_UCX_ROOTHUB_GET_20PORT_INFO, PEVT_UCX_ROOTHUB_GET_20PORT_INFO callback function pointer [Buses], buses.evt_ucx_roothub_get_20port_info, ucxroothub/EvtUcxRootHubGet20PortInfo
f1_keywords:
 - "ucxroothub/PEVT_UCX_ROOTHUB_GET_20PORT_INFO"
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxroothub.h
api_name:
- PEVT_UCX_ROOTHUB_GET_20PORT_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function


## -description


The client driver's implementation that UCX calls when it receives a request for information about USB  2.0 ports on the  root hub.


## -parameters




### -param UcxRootHub [in]

A handle to a UCX object that represents the root hub.


### -param Request [in]

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_20port_info">_ROOTHUB_20PORT_INFO</a>.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188048(v=vs.85)">UcxRootHubCreate</a>
 method.

 The <b>PortInfoArray</b> array of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_20ports_info">_ROOTHUB_20PORTS_INFO</a> structure
    contains a list of USB 2.0 ports that the root hub supports.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
RootHub_EvtRootHubGet20PortInfo(
    UCXROOTHUB         UcxRootHub,
    WDFREQUEST         Request
)
/*++

    For sample demonstration purposes, this function returns statically
    defined information for the single 2.0 port.

--*/
{
    PUCX_ROOTHUB_CONTEXT    ucxRootHubContext;
    WDF_REQUEST_PARAMETERS  wdfRequestParams;
    PROOTHUB_20PORTS_INFO   rootHub20PortsInfo;
    NTSTATUS                status;

    ucxRootHubContext = GetUcxRootHubContext(UcxRootHub);

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(Request, &wdfRequestParams);

    rootHub20PortsInfo = (PROOTHUB_20PORTS_INFO)wdfRequestParams.Parameters.Others.Arg1;

    if (rootHub20PortsInfo->Size < sizeof(ROOTHUB_20PORTS_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_20PORTS_INFO Size %d", rootHub20PortsInfo->Size);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet20PortInfoEnd;
    }

    if (rootHub20PortsInfo->NumberOfPorts != ucxRootHubContext->NumberOf20Ports) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_20PORTS_INFO NumberOfPorts %d", rootHub20PortsInfo->NumberOfPorts);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet20PortInfoEnd;
    }

    if (rootHub20PortsInfo->PortInfoSize < sizeof(ROOTHUB_20PORT_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_20PORT_INFO Size %d", rootHub20PortsInfo->PortInfoSize);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet20PortInfoEnd;
    }

    //
    // Return static root hub 2.0 port information.
    //
    rootHub20PortsInfo->PortInfoArray[0]->PortNumber = ROOTHUB_20_PORT_PORT_NUMBER;
    rootHub20PortsInfo->PortInfoArray[0]->Removable = TriStateTrue;

    status = STATUS_SUCCESS;

    DbgTrace(TL_INFO, RootHub, "RootHub_EvtRootHubGet20PortInfo");

RootHub_EvtRootHubGet20PortInfoEnd:

    WdfRequestComplete(Request, status);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_20ports_info">_ROOTHUB_20PORTS_INFO</a>
 

 

