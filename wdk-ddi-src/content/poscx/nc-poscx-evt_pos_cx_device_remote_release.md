---
UID: NC:poscx.EVT_POS_CX_DEVICE_REMOTE_RELEASE
title: EVT_POS_CX_DEVICE_REMOTE_RELEASE
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_REMOTE_RELEASE callback is called whenever the device is released and left with no owner and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_release.htm
old-project: pos
ms.assetid: F6D60B8C-488A-4A3F-85AE-40A10BF2DC9F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: pos.evt_pos_cx_device_remote_release, EvtPosCxDeviceRemoteRelease callback function, EvtPosCxDeviceRemoteRelease, EVT_POS_CX_DEVICE_REMOTE_RELEASE, EVT_POS_CX_DEVICE_REMOTE_RELEASE, poscx/EvtPosCxDeviceRemoteRelease
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
-	EvtPosCxDeviceRemoteRelease
product: Windows
targetos: Windows
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_REMOTE_RELEASE callback


## -description


The 
  EVT_POS_CX_DEVICE_REMOTE_RELEASE callback is called whenever the device is released and left
with no owner and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.


<a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_claim.md">EVT_POS_CX_DEVICE_REMOTE_CLAIM</a> and <i>EVT_POS_CX_DEVICE_REMOTE_RELEASE</i> add support for remote devices that handle their own claim
semantics.


## -prototype


````
EVT_POS_CX_DEVICE_REMOTE_RELEASE EvtPosCxDeviceRemoteRelease;

NTSTATUS EvtPosCxDeviceRemoteRelease(
  _In_ WDFDEVICE device,
  _In_ ULONG     deviceInterfaceTag
)
{ ... }
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

An identifier used to specify which interface is being released in a multi-function device.  For a single-interface device, this value should be 0.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote release transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.




## -see-also

<a href="..\poscx\nc-poscx-evt_pos_cx_device_remote_claim.md">EVT_POS_CX_DEVICE_REMOTE_CLAIM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20EVT_POS_CX_DEVICE_REMOTE_RELEASE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

