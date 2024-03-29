---
UID: NF:iddcx.IddCxMonitorDeparture
title: IddCxMonitorDeparture function (iddcx.h)
description: An indirect display driver (IDD) calls **IddCxMonitorDeparture** to report a monitor departure from the WDDM graphics adapter.
old-location: display\iddcxmonitordeparture.htm
tech.root: display
ms.date: 01/11/2021
keywords: ["IddCxMonitorDeparture function"]
ms.keywords: IddCxMonitorDeparture, IddCxMonitorDeparture method [Display Devices], display.iddcxmonitordeparture, iddcx/IddCxMonitorDeparture
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: IddCxStub.lib
req.dll: IddCx.dll
req.irql: _Must_inspect_result_
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxMonitorDeparture
 - iddcx/IddCxMonitorDeparture
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorDeparture
---

# IddCxMonitorDeparture function

## -description

An indirect display driver (IDD) calls **IddCxMonitorDeparture** to report a monitor departure from the WDDM graphics adapter.

## -parameters

### -param MonitorObject [in]

The [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object for the monitor that is departing.

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md) creates the [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object for an arriving monitor.

## -see-also

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md)
