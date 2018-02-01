---
UID: NC:spbcx.EVT_SPB_TARGET_DISCONNECT
title: EVT_SPB_TARGET_DISCONNECT
author: windows-driver-content
description: An SPB controller driver's EvtSpbTargetDisconnect event callback function closes a connection to a target device that was previously opened by a call to the driver's EvtSpbTargetConnect event callback function.
old-location: spb\evtspbtargetdisconnect.htm
old-project: SPB
ms.assetid: 02756C35-E76C-42C0-80FA-359CADE224A1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB.evtspbtargetdisconnect, EvtSpbTargetDisconnect callback function [Buses], EvtSpbTargetDisconnect, EVT_SPB_TARGET_DISCONNECT, EVT_SPB_TARGET_DISCONNECT, spbcx/EvtSpbTargetDisconnect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Spbcx.h
apiname:
-	EvtSpbTargetDisconnect
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_LIST_ENTRY, *PSPB_TRANSFER_LIST_ENTRY
req.product: Windows 10 or later.
---

# EVT_SPB_TARGET_DISCONNECT callback


## -description


An SPB controller driver's <i>EvtSpbTargetDisconnect</i> event callback function closes a connection to a target device that was previously opened by a call to the driver's  <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> event callback function.


## -prototype


````
EVT_SPB_TARGET_DISCONNECT EvtSpbTargetDisconnect;

VOID EvtSpbTargetDisconnect(
  _In_ WDFDEVICE Controller,
  _In_ SPBTARGET Target
)
{ ... }
````


## -parameters




### -param Controller [in]

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.


### -param Target [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target to close. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.


## -returns


None.



## -remarks


Implementation of this function by the SPB controller driver is optional.

SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbTargetDisconnect</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller driver sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request to close an SPBTARGET handle. This handle represents a connection to a target device on the bus that the client opened in a previous <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request. If the <i>EvtSpbTargetDisconnect</i> function returns an error code, SpbCx fails the <b>IRP_MJ_CLOSE</b> request.

The <i>EvtSpbTargetDisconnect</i> function is called synchronously from the context of the client's closing thread after all client-initiated I/O operations have ended and after the client has unlocked the controller (if the client previously locked the controller).

If the SPB controller driver has allocated I/O requests and sent them to the next-lower driver in the I/O-request chain for the target device, the <i>EvtSpbTargetDisconnect</i> function should cancel these requests before it returns.

A client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543233">DispatchCleanup</a> and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff559951">CreateProcessNotifyEx</a> callback routines can be called at any time after the <i>EvtSpbTargetDisconnect</i> callback returns. When the client driver's process exits, its <i>CreateProcessNotifyEx</i> routine is called just before the last thread to exit the process is destroyed.

To register an <i>EvtSpbTargetDisconnect</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>

<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20EVT_SPB_TARGET_DISCONNECT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

