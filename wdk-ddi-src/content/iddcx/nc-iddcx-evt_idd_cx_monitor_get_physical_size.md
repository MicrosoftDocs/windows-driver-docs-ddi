---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE
title: EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE
author: windows-driver-content
description: The OS calls EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE to query the physical size of a remote EDID-less monitor.
tech.root: display
ms.assetid: 7dbf3d45-c850-4949-b13b-6548869070f3
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: iddcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - iddcx.h
api_name: 
 - EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE
product: 
 - Windows
targetos: Windows
ms.custom: rs6
---

# EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE callback function

## -description

The OS calls EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE to query the physical size of a remote EDID-less monitor.

## -prototype

```
//Declaration

EVT_IDD_CX_MONITOR_GET_PHYSICAL_SIZE EvtIddCxMonitorGetPhysicalSize; 

// Definition

NTSTATUS EvtIddCxMonitorGetPhysicalSize 
(
	IDDCX_MONITOR MonitorObject
	IDARG_OUT_MONITORGETPHYSICALSIZE * pOutArgs
)
{...}

```

## -parameters

### -param MonitorObject

[in] The context for the monitor this OPM context should be created on.

### -param pOutArgs

[out] Pointer to a [IDARG_OUT_MONITORGETPHYSICALSIZE](ns-iddcx-idarg_out_monitorgetphysicalsize.md) structure that contains information about the monitor size.

## -returns

If the driver knows the physical size of the monitor, it should fill in the *pOutArgs* and return STATUS_SUCCESS. In the event the driver does not know the physical size, it should return STATUS_NO_DATA_DETECTED.

## -remarks

This callback is only called for remote drivers that do not provide a monitor description for the specified monitor. If a remote driver does specify a monitor description for a given monitor, then the physical width and height will be taken from the description and this callback will not be called for that monitor.

**To declare a remote ID driver:**

An ID driver declares that it wants to create a remote ID adapter by setting the [**IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER**](ne-iddcx-iddcx_adapter_flags.md) bit in the [IDDCX_ADAPTER_CAPS](ns-iddcx-iddcx_adapter_caps.md).**Flags** field when calling the [IddCxAdapterInitAsync](iddcx\nf-iddcx-iddcxadapterinitasync.md) function. The OS tracks if the ID driver is being loaded due to the remote desktop stack connecting a remote session and will fail the IddCxAdapterInitAsync() call in the following two cases:

* If an ID driver does not set the IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER flags for a device that was created by the OS remote desktop stack for a remote session
* If an ID driver sets the IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER flags for a device that was not created by the OS remote desktop stack

## -see-also