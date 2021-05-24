---
UID: NC:dispmprt.DXGKCB_LOG_ETW_EVENT
title: DXGKCB_LOG_ETW_EVENT (dispmprt.h)
description: The DxgkCbLogEtwEvent function logs an Event Tracing for Windows (ETW) event.
old-location: display\dxgkcblogetwevent.htm
tech.root: display
ms.date: 05/13/2021
keywords: ["DXGKCB_LOG_ETW_EVENT callback function"]
ms.keywords: DXGKCB_LOG_ETW_EVENT, DXGKCB_LOG_ETW_EVENT callback, DpFunctions_1e074b6d-dff4-4d1f-93ce-4333a4241562.xml, DxgkCbLogEtwEvent, DxgkCbLogEtwEvent callback function [Display Devices], display.dxgkcblogetwevent, dispmprt/DxgkCbLogEtwEvent
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_LOG_ETW_EVENT
 - dispmprt/DXGKCB_LOG_ETW_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_LOG_ETW_EVENT
---

# DXGKCB_LOG_ETW_EVENT callback function

## -description

The **DxgkCbLogEtwEvent** function logs an Event Tracing for Windows (ETW) event.

## -parameters

### -param EventGuid

[in] A GUID that identifies the event to be logged.

### -param Type

[in] A constant that specifies the event type. These constants are defined in *Evntrace.h* and have the form of **EVENT_TRACE_TYPE_XX**.

### -param EventBufferSize

[in] The size, in bytes, of the buffer pointed to by **EventBuffer**. There is a significant performance penalty if the buffer is larger than 256 bytes.

### -param EventBuffer

[in] A pointer to a buffer that contains the information to be logged. This parameter can be NULL, or a pointer to the following structure type depending on the value of **EventGuid**.

## -remarks

If event logging is not enabled, **DxgkCbLogEtwEvent** returns immediately without logging the event.

To enable or disable event logging, call the [**DxgkDdiControlEtwLogging**](nc-dispmprt-dxgkddi_control_etw_logging.md) function.

If **EventBufferSize** is less than or equal to 256, **DxgkCbLogEtwEvent** can be called an any IRQL. If **EventBufferSize** is greater than 256, **DxgkCbLogEtwEvent** must be called at IRQL = PASSIVE_LEVEL.

### Example: Logging an event with the event logger

The following code example shows how to log an event with the event logger.

```cpp
// {A7BF27A0-7401-4733-9FED-FDB51067FECC}
DEFINE_GUID(R200_DUMMY_LOGGING,
0xa7bf27a0, 0x7401, 0x4733, 0x9f, 0xed, 0xfd, 0xb5, 0x10, 0x67, 0xfe, 0xcc);

VOID
DummyTrace(
    HW_DEVICE_EXTENSION* Adapter
    )
{
    Adapter->ddiCallback.DxgkCbLogEtwEvent(&R200_DUMMY_LOGGING,
  EVENT_TRACE_TYPE_INFO,
  0,
  NULL);
}
```

### Logging Azure driver events

Starting in Windows Server 2022 (WDDM 2.9), a graphics driver's  **DxgkCbLogEtwEvent** callback function can expose important events relevant to Azure triage and monitoring. As Azure adds vGPU offerings, it will become more important to have a mechanism to expose important events that the driver sees. Particularly important for monitoring and health is the exposure of function-level resets (VF TDRs) and whole-GPU resets (adapter-wide TDRs). In the future, this framework will allow the OS to expose additional important events that may involve driver-specific behaviors that have triage value when issues arrive.

A driver should use the following GUID to report specific Azure driver events:

``` cpp

DEFINE_GUID(GUID_DXGKDDI_AZURE_TRIAGE_EVENT,
0x45125F6F, 0x6132, 0x4082, 0xAD, 0x17, 0xED, 0x27, 0xF8, 0xDD, 0x02, 0xF9);
```

These events are used by the graphics kernel components to feed triage information into standard Azure monitoring pipelines used for incident triage. They integrate with other graphics events also being exposed to build machine event histories and expose useful queries to be used in the monitoring of the health of the host and the VMs it supports.

When this GUID is used, **EventBuffer** points to a [**DXGKARG_PARTITIONING_EVENT_NOTIFICATION**](../d3dkmddi/ns-d3dkmddi-dxgkddicb_partitioning_event_notification.md) structure.

## -see-also

[**DXGKARG_PARTITIONING_EVENT_NOTIFICATION**](../d3dkmddi/ns-d3dkmddi-dxgkddicb_partitioning_event_notification.md)

[**DxgkDdiControlEtwLogging**](nc-dispmprt-dxgkddi_control_etw_logging.md)
