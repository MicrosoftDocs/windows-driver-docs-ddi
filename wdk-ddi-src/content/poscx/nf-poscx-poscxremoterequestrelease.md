---
UID: NF:poscx.PosCxRemoteRequestRelease
title: PosCxRemoteRequestRelease function (poscx.h)
description: PosCxRemoteRequestRelease is called whenever a remote device asks for the device to release. This initiates claim negotiation.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxRemoteRequestRelease function"]
ms.keywords: PosCxRemoteRequestRelease, PosCxRemoteRequestRelease function, pos.poscxremoterequestrelease, poscx/PosCxRemoteRequestRelease
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
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxRemoteRequestRelease
 - poscx/PosCxRemoteRequestRelease
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxRemoteRequestRelease
---

## -description

PosCxRemoteRequestRelease is called whenever a remote device asks for the device to release. This initiates claim negotiation.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param deviceInterfaceTag [in]

The device interface that initiated the release request.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The device will now start resolving the remote request to release. |
| **STATUS_DEVICE_NOT_READY** | The PosCx library was not successfully initialized. |
