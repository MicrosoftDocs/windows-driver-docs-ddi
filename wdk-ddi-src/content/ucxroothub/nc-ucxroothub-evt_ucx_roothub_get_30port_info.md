---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_GET_30PORT_INFO
title: EVT_UCX_ROOTHUB_GET_30PORT_INFO
author: windows-driver-content
description: The client driver's implementation that UCX calls when it receives a request for information about USB 3.0 ports on the root hub.
old-location: buses\evt_ucx_roothub_get_30port_info.htm
old-project: usbref
ms.assetid: 35eb22aa-3158-48ad-a20c-909604f9b4b1
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.evt_ucx_roothub_get_30port_info, EvtUcxRootHubGet30PortInfo callback function [Buses], EvtUcxRootHubGet30PortInfo, EVT_UCX_ROOTHUB_GET_30PORT_INFO, EVT_UCX_ROOTHUB_GET_30PORT_INFO, ucxroothub/EvtUcxRootHubGet30PortInfo, PEVT_UCX_ROOTHUB_GET_30PORT_INFO callback function pointer [Buses], PEVT_UCX_ROOTHUB_GET_30PORT_INFO
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
-	PEVT_UCX_ROOTHUB_GET_30PORT_INFO
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
req.product: Windows 10 or later.
---

# EVT_UCX_ROOTHUB_GET_30PORT_INFO callback


## -description


The client driver's implementation that UCX calls when it receives a request for information about USB  3.0 ports on the  root hub.


## -prototype


````
EVT_UCX_ROOTHUB_GET_30PORT_INFO EvtUcxRootHubGet30PortInfo;

VOID EvtUcxRootHubGet30PortInfo(
  _In_ UCXROOTHUB UcxRootHub,
  _In_ WDFREQUEST Request
)
{ ... }

typedef EVT_UCX_ROOTHUB_GET_30PORT_INFO PEVT_UCX_ROOTHUB_GET_30PORT_INFO;
````


## -parameters




### -param UcxRootHub [in]

A handle to a UCX object that represents the root hub.


### -param Request [in]

A structure of type <a href="..\ucxroothub\ns-ucxroothub-_roothub_30port_info.md">_ROOTHUB_30PORT_INFO</a>.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
 method.

 The <b>PortInfoArray</b> array of the <a href="..\ucxroothub\ns-ucxroothub-_roothub_30port_info.md">_ROOTHUB_30PORT_INFO</a> structure
    contains a list of USB 3.0 ports that the root hub supports.

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
RootHub_EvtRootHubGet30PortInfo(
    UCXROOTHUB         UcxRootHub,
    WDFREQUEST         Request
)
/*++

    For sample demonstration purposes, this function returns statically
    defined information for the single 3.0 port.

--*/
{
    PUCX_ROOTHUB_CONTEXT    ucxRootHubContext;
    WDF_REQUEST_PARAMETERS  wdfRequestParams;
    PROOTHUB_30PORTS_INFO   rootHub30PortsInfo;
    NTSTATUS                status;

    ucxRootHubContext = GetUcxRootHubContext(UcxRootHub);

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(Request, &amp;wdfRequestParams);

    rootHub30PortsInfo = (PROOTHUB_30PORTS_INFO)wdfRequestParams.Parameters.Others.Arg1;

    if (rootHub30PortsInfo-&gt;Size &lt; sizeof(ROOTHUB_30PORTS_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_30PORTS_INFO Size %d", rootHub30PortsInfo-&gt;Size);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet30PortInfoEnd;
    }

    if (rootHub30PortsInfo-&gt;NumberOfPorts != ucxRootHubContext-&gt;NumberOf30Ports) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_30PORTS_INFO NumberOfPorts %d", rootHub30PortsInfo-&gt;NumberOfPorts);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet30PortInfoEnd;
    }

    if (rootHub30PortsInfo-&gt;PortInfoSize &lt; sizeof(ROOTHUB_30PORT_INFO)) {
        DbgTrace(TL_ERROR, RootHub, "Invalid ROOTHUB_30PORT_INFO Size %d", rootHub30PortsInfo-&gt;PortInfoSize);
        status = STATUS_INVALID_PARAMETER;
        goto RootHub_EvtRootHubGet30PortInfoEnd;
    }

    //
    // Return static root hub 3.0 port information.
    //
    rootHub30PortsInfo-&gt;PortInfoArray[0]-&gt;PortNumber = ROOTHUB_30_PORT_PORT_NUMBER;
    rootHub30PortsInfo-&gt;PortInfoArray[0]-&gt;Removable = TriStateTrue;

    status = STATUS_SUCCESS;

    DbgTrace(TL_INFO, RootHub, "RootHub_EvtRootHubGet30PortInfo");

RootHub_EvtRootHubGet30PortInfoEnd:

    WdfRequestComplete(Request, status);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_30port_info.md">_ROOTHUB_30PORT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

