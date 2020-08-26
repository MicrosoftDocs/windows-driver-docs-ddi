---
UID: NC:poscx.EVT_POS_CX_DEVICE_REMOTE_RETAIN
title: EVT_POS_CX_DEVICE_REMOTE_RETAIN (poscx.h)
description: The EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim on a network device and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_retain.htm
tech.root: pos
ms.assetid: 9B23DB23-D995-4737-9302-872F2144823D
ms.date: 02/23/2018
keywords: ["EVT_POS_CX_DEVICE_REMOTE_RETAIN callback function"]
ms.keywords: EVT_POS_CX_DEVICE_REMOTE_RETAIN, EVT_POS_CX_DEVICE_REMOTE_RETAIN callback, EvtPosCxDeviceRemoteRetain, EvtPosCxDeviceRemoteRetain callback function, pos.evt_pos_cx_device_remote_retain, poscx/EvtPosCxDeviceRemoteRetain
f1_keywords:
 - "poscx/EvtPosCxDeviceRemoteRetain"
 - "EvtPosCxDeviceRemoteRetain"
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
- EvtPosCxDeviceRemoteRetain
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_REMOTE_RETAIN callback function


## -description


The 
  EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim
on a network device and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.


## -parameters




### -param device 
[in]
A handle to a framework device object that represents the device.


### -param deviceInterfaceTag 
[in]
An identifier used to specify which interface is being retained in a multi-function device.  For a single-interface device, this value should be 0.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.

If the driver is unable to complete the remote retain transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.



