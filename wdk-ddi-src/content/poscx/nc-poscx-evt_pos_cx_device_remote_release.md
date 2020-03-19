---
UID: NC:poscx.EVT_POS_CX_DEVICE_REMOTE_RELEASE
title: EVT_POS_CX_DEVICE_REMOTE_RELEASE (poscx.h)
description: The EVT_POS_CX_DEVICE_REMOTE_RELEASE callback is called whenever the device is released and left with no owner and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_release.htm
tech.root: pos
ms.assetid: F6D60B8C-488A-4A3F-85AE-40A10BF2DC9F
ms.date: 02/23/2018
keywords: ["EVT_POS_CX_DEVICE_REMOTE_RELEASE callback function"]
ms.keywords: EVT_POS_CX_DEVICE_REMOTE_RELEASE, EVT_POS_CX_DEVICE_REMOTE_RELEASE callback, EvtPosCxDeviceRemoteRelease, EvtPosCxDeviceRemoteRelease callback function, pos.evt_pos_cx_device_remote_release, poscx/EvtPosCxDeviceRemoteRelease
f1_keywords:
 - "poscx/EvtPosCxDeviceRemoteRelease"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- poscx.h
api_name:
- EvtPosCxDeviceRemoteRelease
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_REMOTE_RELEASE callback function


## -description


The 
  EVT_POS_CX_DEVICE_REMOTE_RELEASE callback is called whenever the device is released and left
with no owner and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nc-poscx-evt_pos_cx_device_remote_claim">EVT_POS_CX_DEVICE_REMOTE_CLAIM</a> and <i>EVT_POS_CX_DEVICE_REMOTE_RELEASE</i> add support for remote devices that handle their own claim
semantics.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

An identifier used to specify which interface is being released in a multi-function device.  For a single-interface device, this value should be 0.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote release transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nc-poscx-evt_pos_cx_device_remote_claim">EVT_POS_CX_DEVICE_REMOTE_CLAIM</a>
 

 

