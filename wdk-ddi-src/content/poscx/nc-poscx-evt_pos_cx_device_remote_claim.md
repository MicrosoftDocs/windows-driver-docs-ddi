---
UID: NC:poscx.EVT_POS_CX_DEVICE_REMOTE_CLAIM
title: EVT_POS_CX_DEVICE_REMOTE_CLAIM
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_REMOTE_CLAIM callback is called when the device is transitioning from unclaimed to claimed and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_claim.htm
old-project: pos
ms.assetid: 3D8907A2-E53E-40D9-870A-AF0EB062E81F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.evt_pos_cx_device_remote_claim, EvtPosCxDeviceRemoteClaim callback function, EvtPosCxDeviceRemoteClaim, EVT_POS_CX_DEVICE_REMOTE_CLAIM, EVT_POS_CX_DEVICE_REMOTE_CLAIM, poscx/EvtPosCxDeviceRemoteClaim
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	poscx.h
apiname:
-	EvtPosCxDeviceRemoteClaim
product: Windows
targetos: Windows
req.typenames: "*PPCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR"
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_REMOTE_CLAIM callback


## -description


The 
  EVT_POS_CX_DEVICE_REMOTE_CLAIM callback is called when the device is transitioning from
unclaimed to claimed and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.

<i>EVT_POS_CX_DEVICE_REMOTE_CLAIM</i> and <a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md">EVT_POS_CX_DEVICE_REMOTE_RELEASE</a> add support for remote devices that handle their own claim
semantics.


## -prototype


````
EVT_POS_CX_DEVICE_REMOTE_CLAIM EvtPosCxDeviceRemoteClaim;

NTSTATUS EvtPosCxDeviceRemoteClaim(
  _In_ WDFDEVICE device,
  _In_ ULONG     deviceInterfaceTag
)
{ ... }
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

An identifier used to specify which interface is being claimed in a multi-function device.  For a single-interface device, this value should be 0.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote claim transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.




## -see-also

<a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md">EVT_POS_CX_DEVICE_REMOTE_RELEASE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20EVT_POS_CX_DEVICE_REMOTE_CLAIM callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

