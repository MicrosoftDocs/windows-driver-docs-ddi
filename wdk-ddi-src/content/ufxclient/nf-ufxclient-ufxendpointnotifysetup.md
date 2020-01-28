---
UID: NF:ufxclient.UfxEndpointNotifySetup
title: UfxEndpointNotifySetup function (ufxclient.h)
description: Notifies UFX when the client driver receives a setup packet from the host.
old-location: buses\ufxendpointnotifysetup.htm
tech.root: usbref
ms.assetid: 147CE46A-315D-4B75-B345-A7C0B01B2078
ms.date: 05/07/2018
ms.keywords: UfxEndpointNotifySetup, UfxEndpointNotifySetup method [Buses], buses.ufxendpointnotifysetup, ufxclient/UfxEndpointNotifySetup
f1_keywords:
 - "ufxclient/UfxEndpointNotifySetup"
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ufxclient.h
api_name:
- UfxEndpointNotifySetup
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxEndpointNotifySetup function


## -description


Notifies UFX when the client driver receives a setup packet from the host.


## -parameters




### -param UfxEndpoint

<p>A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate"><b>UfxDeviceCreate</b></a>.</p>


### -param SetupInfo [in]

A pointer to a USB setup packet described in a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure (defined in Usbspec.h).


## -remarks



The following example shows how to handle setup packet completion.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    if (ControlContext->SetupRequested) {
        TRACE_TRANSFER("COMPLETE (Setup)", Endpoint, NULL);
        
        ControlContext->SetupRequested = FALSE;
        TransferContext->TransferStarted = FALSE;

        UfxEndpointNotifySetup(Endpoint, ControlContext->SetupPacket);

    } 
</pre>
</td>
</tr>
</table></span></div>


