---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_CONTROL_URB
title: EVT_UCX_ROOTHUB_CONTROL_URB
author: windows-driver-content
description: The client driver uses this callback type to implement handlers that UCX calls when it receives feature control requests on the USB hub.
old-location: buses\evt_ucx_roothub_control_urb.htm
old-project: usbref
ms.assetid: 4463a68f-ef03-43a1-b3e2-7baf43f47e80
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_ROOTHUB_CONTROL_URB, EvtUcxRootHubControlUrb, EvtUcxRootHubControlUrb callback function [Buses], PEVT_UCX_ROOTHUB_CONTROL_URB, PEVT_UCX_ROOTHUB_CONTROL_URB callback function pointer [Buses], buses.evt_ucx_roothub_control_urb, ucxroothub/EvtUcxRootHubControlUrb
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxroothub.h
api_name:
-	PEVT_UCX_ROOTHUB_CONTROL_URB
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
req.product: Windows 10 or later.
---

# EVT_UCX_ROOTHUB_CONTROL_URB callback


## -description


The client driver uses this callback type to implement handlers that UCX calls when it receives feature control requests on the USB hub.


## -parameters




### -param UcxRootHub [in]

A handle to a UCX object that represents the root hub.


### -param Request [in]

Contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> for the feature request.


## -returns



This callback function does not return a value.




## -remarks



The client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
 method.

The driver either provides callbacks for all of the individual feature request types, as shown in the first example, or it can provide a single handler of type <i>EVT_UCX_ROOTHUB_CONTROL_URB</i> that UCX calls for all hub and port control transfers.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

This example shows how to register callbacks for individual feature request types.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubClearHubFeature;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubClearPortFeature;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubGetHubStatus;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubGetPortStatus;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubSetHubFeature;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubSetPortFeature;
EVT_UCX_ROOTHUB_CONTROL_URB RootHub_EvtRootHubGetPortErrorCount;

...

    //
    // Create the root hub
    //
    UCX_ROOTHUB_CONFIG_INIT(&amp;ucxRootHubConfig,
                            RootHub_EvtRootHubClearHubFeature,
                            RootHub_EvtRootHubClearPortFeature,
                            RootHub_EvtRootHubGetHubStatus,
                            RootHub_EvtRootHubGetPortStatus,
                            RootHub_EvtRootHubSetHubFeature,
                            RootHub_EvtRootHubSetPortFeature,
                            RootHub_EvtRootHubGetPortErrorCount,
                            RootHub_EvtRootHubInterruptTx,
                            RootHub_EvtRootHubGetInfo,
                            RootHub_EvtRootHubGet20PortInfo,
                            RootHub_EvtRootHubGet30PortInfo);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;objectAttributes, UCX_ROOTHUB_CONTEXT);

    status = UcxRootHubCreate(ucxController,
                              &amp;ucxRootHubConfig,
                              &amp;objectAttributes,
                              &amp;ucxRootHub);
</pre>
</td>
</tr>
</table></span></div>
Here is a sample implementation of one of the URB-specific request handlers.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
RootHub_EvtRootHubClearHubFeature(
    UCXROOTHUB         UcxRootHub,
    WDFREQUEST         ControlUrb
)
/*++

Routine Description:

    UCX calls this routine when it receives a new Clear Hub Feature request.

--*/
{
    UNREFERENCED_PARAMETER(UcxRootHub);

    DbgTrace(TL_INFO, RootHub, "RootHub_EvtRootHubClearHubFeature");

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);
    urb = (PURB)wdfRequestParams.Parameters.Others.Arg1;
    setupPacket = (PWDF_USB_CONTROL_SETUP_PACKET)&amp;urb-&gt;UrbControlTransferEx.SetupPacket[0];
    ...

    WdfRequestComplete(ControlUrb, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
 

 

