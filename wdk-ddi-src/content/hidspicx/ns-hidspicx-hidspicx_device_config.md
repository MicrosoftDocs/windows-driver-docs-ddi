---
UID: NS:hidspicx._HIDSPICX_DEVICE_CONFIG
tech.root: hid
title: HIDSPICX_DEVICE_CONFIG
ms.date: 
targetos: Windows
description: 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: HIDSPICX_DEVICE_CONFIG, *PHIDSPICX_DEVICE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - hidspicx.h
api_name:
 - _HIDSPICX_DEVICE_CONFIG
 - PHIDSPICX_DEVICE_CONFIG
 - HIDSPICX_DEVICE_CONFIG
f1_keywords:
 - _HIDSPICX_DEVICE_CONFIG
 - hidspicx/_HIDSPICX_DEVICE_CONFIG
 - PHIDSPICX_DEVICE_CONFIG
 - hidspicx/PHIDSPICX_DEVICE_CONFIG
 - HIDSPICX_DEVICE_CONFIG
 - hidspicx/HIDSPICX_DEVICE_CONFIG
dev_langs:
 - c++
---

## -description

The **HIDSPICX_DEVICE_CONFIG** structure is used to provide configuration information to HidSpiCx. Instances of this structure must be initialized using the HIDSPICX_DEVICE_CONFIG_INIT function.

## -struct-fields

### -field Size

This should not be explicitly set by the client driver, and will be set by HIDSPICX_DEVICE_CONFIG_INIT.

### -field EvtResetDevice

Function pointer to a client-implemented device reset callback.

### -field EvtNotifyPowerDown

Function pointer to a client-implemented power-down notification callback.

### -field InputReportQueue

WDF handle to a client-created non-power-managed queue for receipt of input report WDFREQUESTS from HidSpiCx. The client may choose how reports are dispatched from this queue (manual, sequential, parallel etc).

The class extension will forward a number of ???ping-pong??? read (IRP_MJ_READ) requests (as specified by the client in its configuration structure) to the provided input report queue, at IRQL <= DISPATCH_LEVEL. These requests may be programmed directly into hardware (through DMA etc) by the client driver, or selectively dequeued upon input from the peripheral device, and buffer copied into. When the peripheral device interrupts to provide a report, the client driver reads the report data, and a ping-pong is completed by the client driver to the class extension with the report body from the peripheral device. The size of the report buffers is automatically calculated by the class extension, on the basis of the peripheral device descriptor (or a default size before device descriptor retrieval).

Requests may be completed by the client driver at IRQL <= DISPATCH_LEVEL. When a request is completed by the client driver, the class extension will send another request to the queue (or re-send) synchronously in the context of the request completion. The information of the requests should be set to the total bytes read from the device into the buffer (sizeof(HIDSPICX_REPORT) + ReportContentLength).

In the event of a read error from the peripheral device (e.g. invalid or malformed data), the client driver may complete one of these ping pong requests with an error code and no data, or use the provided  HidSpiCxNotifyDeviceReset DDI to inform the class extension of the need for a host initiated reset to occur.

The class extension will cancel and re-send these requests at runtime when the buffer size changes (as part of startup / reset device descriptor retrieval flows).

It is possible in certain cases (for devices not fully conforming to the protocol) for a report to be received from the device when there are no reads pending in the queue. If this is the case, the client shall notify the Cx that the device needs a reset using the HidSpiCxNotifyDeviceReset DDI, and either discard or not read the report from the device.

### -field OutputReportQueue

WDF handle to a client-created non-power-managed queue for receipt of output report WDFREQUESTS from HidSpiCx. The client may choose how reports are dispatched from this queue (manual, sequential, parallel etc).

The class extension will forward output (IRP_MJ_WRITE) requests to the output report queue to instruct the client driver to write a HIDSPI output report to the device. These requests may be forwarded at IRQL <= DISPATCH_LEVEL. The client driver should write the report to the bus, and complete the request with an appropriate status to indicate success or failure. On success, the request information should be set to the size of the output buffer.

### -field NumberOfInputReportRequestsToPend

Optional parameter, specifying how many requests are to be pended in the Input Report Queue at a given time. If this is zero, the class extension will choose a default.

### -field Reserved

Must be zero, and should not be explicitly set by client drivers.

## -remarks

## -see-also
