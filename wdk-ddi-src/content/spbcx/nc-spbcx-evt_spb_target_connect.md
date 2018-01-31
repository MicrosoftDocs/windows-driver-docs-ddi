---
UID: NC:spbcx.EVT_SPB_TARGET_CONNECT
title: EVT_SPB_TARGET_CONNECT
author: windows-driver-content
description: An SPB controller driver's EvtSpbTargetConnect event callback function opens a connection to a target device on the bus.
old-location: spb\evtspbtargetconnect.htm
old-project: SPB
ms.assetid: D90DD169-A989-4D08-B1B8-BDE7EC9B7A82
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB.evtspbtargetconnect, EvtSpbTargetConnect callback function [Buses], EvtSpbTargetConnect, EVT_SPB_TARGET_CONNECT, EVT_SPB_TARGET_CONNECT, spbcx/EvtSpbTargetConnect
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
-	EvtSpbTargetConnect
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_LIST_ENTRY, *PSPB_TRANSFER_LIST_ENTRY
req.product: Windows 10 or later.
---

# EVT_SPB_TARGET_CONNECT callback


## -description


An SPB controller driver's <i>EvtSpbTargetConnect</i> event callback function opens a connection to a target device on the bus.


## -prototype


````
EVT_SPB_TARGET_CONNECT EvtSpbTargetConnect;

NTSTATUS EvtSpbTargetConnect(
  _In_ WDFDEVICE Controller,
  _In_ SPBTARGET Target
)
{ ... }
````


## -parameters




#### - Controller [in]

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.


#### - Target [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target to open.  The target is a peripheral device or port that is attached to the bus.


## -returns


<i>EvtSpbTargetConnect</i> returns STATUS_SUCCESS if the driver successfully opens the connection to the target.  Otherwise, the function returns an appropriate NTSTATUS error code.



## -remarks


Implementation of this function by the SPB controller driver is optional.

The SPB framework extension (SpbCx) manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbTargetConnect</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request to open a connection to a target device on the bus. If the <i>EvtSpbTargetConnect</i> function returns an error code, SpbCx fails the <b>IRP_MJ_CREATE</b> request. A client that successfully opens a connection to a target has exclusive access to the target until the connection is closed.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a> method to get the connection parameters for the target device. An SPB controller driver typically calls this method from the driver's <i>EvtSpbTargetConnect</i> function. <b>SpbTargetGetConnectionParameters</b> writes the connection parameters to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a> structure. The <b>ConnectionParameters</b> member of this structure is a pointer to a buffer that contains the connection settings for the target device. The driver uses these settings to configure the SPB controller to communicate with the device. For more information, see <a href="https://msdn.microsoft.com/B614993A-0EA9-4B91-A336-80EEF9BE3E69">How to Get the Connection Settings for a Device</a>.

The <i>EvtSpbTargetConnect</i> callback function is called synchronously from the context of the client thread that requests the connection to the target.

SpbCx calls the <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> callback function to close a target connection that was previously opened by an <i>EvtSpbTargetConnect</i> callback.

To register an <i>EvtSpbTargetConnect</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>

<a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20EVT_SPB_TARGET_CONNECT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

