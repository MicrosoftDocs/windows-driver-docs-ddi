---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_GET_INFO
title: EVT_UCX_ROOTHUB_GET_INFO
author: windows-driver-content
description: The client driver's implementation that UCX calls when it receives a request for information about the root hub.
old-location: buses\evt_ucx_roothub_get_info.htm
old-project: usbref
ms.assetid: b882b401-f806-4334-a8c5-fa65382fb9d3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_ROOTHUB_GET_INFO, EvtUcxRootHubGetInfo, EvtUcxRootHubGetInfo callback function [Buses], PEVT_UCX_ROOTHUB_GET_INFO, PEVT_UCX_ROOTHUB_GET_INFO callback function pointer [Buses], buses.evt_ucx_roothub_get_info, ucxroothub/EvtUcxRootHubGetInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxroothub.h
apiname:
-	PEVT_UCX_ROOTHUB_GET_INFO
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
req.product: Windows 10 or later.
---

# EVT_UCX_ROOTHUB_GET_INFO callback


## -description


The client driver's implementation that UCX calls when it receives a request for information about the root hub.


## -prototype


````
EVT_UCX_ROOTHUB_GET_INFO EvtUcxRootHubGetInfo;

VOID EvtUcxRootHubGetInfo(
  _In_ UCXROOTHUB UcxRootHub,
  _In_ WDFREQUEST Request
)
{ ... }

typedef EVT_UCX_ROOTHUB_GET_INFO PEVT_UCX_ROOTHUB_GET_INFO;
````


## -parameters




### -param UcxRootHub [in]

A handle to a UCX object that represents the root hub.


### -param Request [in]

A structure of type <a href="..\ucxroothub\ns-ucxroothub-_roothub_info.md">ROOTHUB_INFO</a>.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
 method.

The <a href="..\ucxroothub\ns-ucxroothub-_roothub_info.md">_ROOTHUB_INFO</a> structure contains the number of USB 2.0 and USB 3.0 ports supported by the root hub.

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

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(Request, &amp;wdfRequestParams);

    rootHubInfo = (PROOTHUB_INFO)wdfRequestParams.Parameters.Others.Arg1;

    if (rootHubInfo-&gt;Size &lt; sizeof(ROOTHUB_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_INFO Size %d", rootHubInfo-&gt;Size);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGetInfo;
    }

    rootHubInfo-&gt;ControllerType = ControllerTypeSoftXhci;
    rootHubInfo-&gt;NumberOf20Ports = ucxRootHubContext-&gt;NumberOf20Ports;
    rootHubInfo-&gt;NumberOf30Ports = ucxRootHubContext-&gt;NumberOf30Ports;
    rootHubInfo-&gt;MaxU1ExitLatency = ucxRootHubContext-&gt;U1DeviceExitLatency;
    rootHubInfo-&gt;MaxU2ExitLatency = ucxRootHubContext-&gt;U2DeviceExitLatency;

    DbgTrace(TL_INFO, RootHub, "RootHub_UcxEvtGetInfo NumberOf20Ports %d NumberOf30Ports %d", rootHubInfo-&gt;NumberOf20Ports, rootHubInfo-&gt;NumberOf30Ports);

    status = STATUS_SUCCESS;

RootHub_EvtRootHubGetInfo:

    WdfRequestComplete(Request, status);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_info.md">_ROOTHUB_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ROOTHUB_GET_INFO callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

