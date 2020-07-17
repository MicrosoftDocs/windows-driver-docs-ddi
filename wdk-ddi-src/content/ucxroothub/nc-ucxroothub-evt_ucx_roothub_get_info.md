---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_GET_INFO
title: EVT_UCX_ROOTHUB_GET_INFO (ucxroothub.h)
description: The client driver's implementation that UCX calls when it receives a request for information about the root hub.
old-location: buses\evt_ucx_roothub_get_info.htm
tech.root: usbref
ms.assetid: b882b401-f806-4334-a8c5-fa65382fb9d3
ms.date: 05/07/2018
keywords: ["EVT_UCX_ROOTHUB_GET_INFO callback function"]
ms.keywords: EVT_UCX_ROOTHUB_GET_INFO, EVT_UCX_ROOTHUB_GET_INFO callback, EvtUcxRootHubGetInfo, EvtUcxRootHubGetInfo callback function [Buses], PEVT_UCX_ROOTHUB_GET_INFO, PEVT_UCX_ROOTHUB_GET_INFO callback function pointer [Buses], buses.evt_ucx_roothub_get_info, ucxroothub/EvtUcxRootHubGetInfo
f1_keywords:
 - "ucxroothub/PEVT_UCX_ROOTHUB_GET_INFO"
 - "PEVT_UCX_ROOTHUB_GET_INFO"
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
- PEVT_UCX_ROOTHUB_GET_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ROOTHUB_GET_INFO callback function


## -description


The client driver's implementation that UCX calls when it receives a request for information about the root hub.


## -parameters




### -param UcxRootHub [in]

A handle to a UCX object that represents the root hub.


### -param Request [in]

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_info">ROOTHUB_INFO</a>.


## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188048(v=vs.85)">UcxRootHubCreate</a>
 method.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_info">_ROOTHUB_INFO</a> structure contains the number of USB 2.0 and USB 3.0 ports supported by the root hub.

After UCX calls  the <i>EVT_UCX_ROOTHUB_GET_INFO</i> function, the number of ports exposed by the root hub is guaranteed to remain the same. Note that these are virtual ports, not physical ports.  Each physical USB connector is represented by one or more 
ports of different speed on the root hub.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
RootHub_EvtRootHubGetInfo(
    UCXROOTHUB         UcxRootHub,
    WDFREQUEST         Request
)
/*++

    For sample demonstration purposes, this function returns statically
    defined information for the root hub.

--*/
{
    PUCX_ROOTHUB_CONTEXT    ucxRootHubContext;
    WDF_REQUEST_PARAMETERS  wdfRequestParams;
    PROOTHUB_INFO           rootHubInfo;
    NTSTATUS                status;

    ucxRootHubContext = GetUcxRootHubContext(UcxRootHub);

    WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
    WdfRequestGetParameters(Request, &wdfRequestParams);

    rootHubInfo = (PROOTHUB_INFO)wdfRequestParams.Parameters.Others.Arg1;

    if (rootHubInfo->Size < sizeof(ROOTHUB_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_INFO Size %d", rootHubInfo->Size);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGetInfo;
    }

    rootHubInfo->ControllerType = ControllerTypeSoftXhci;
    rootHubInfo->NumberOf20Ports = ucxRootHubContext->NumberOf20Ports;
    rootHubInfo->NumberOf30Ports = ucxRootHubContext->NumberOf30Ports;
    rootHubInfo->MaxU1ExitLatency = ucxRootHubContext->U1DeviceExitLatency;
    rootHubInfo->MaxU2ExitLatency = ucxRootHubContext->U2DeviceExitLatency;

    DbgTrace(TL_INFO, RootHub, "RootHub_UcxEvtGetInfo NumberOf20Ports %d NumberOf30Ports %d", rootHubInfo->NumberOf20Ports, rootHubInfo->NumberOf30Ports);

    status = STATUS_SUCCESS;

RootHub_EvtRootHubGetInfo:

    WdfRequestComplete(Request, status);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_info">_ROOTHUB_INFO</a>
 

 

