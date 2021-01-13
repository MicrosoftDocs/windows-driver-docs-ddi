---
UID: NF:iddcx.IddCxMonitorArrival
title: IddCxMonitorArrival function (iddcx.h)
description: An OS callback function the driver calls to report a monitor arrival on the WDDM graphics adapter.
old-location: display\iddcxmonitorarrival.htm
tech.root: display
ms.date: 01/11/2021
keywords: ["IddCxMonitorArrival function"]
ms.keywords: IddCxMonitorArrival, IddCxMonitorArrival method [Display Devices], display.iddcxmonitorarrival, iddcx/IddCxMonitorArrival
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
 - IddCxMonitorArrival
 - iddcx/IddCxMonitorArrival
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorArrival
---

# IddCxMonitorArrival function

## -description

An indirect display driver (IDD) calls **IddCxMonitorArrival** to report a monitor arrival on the WDDM graphics adapter.

## -parameters

### -param AdapterObject

[in] The [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object for the monitor that arrived.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_MONITORARRIVAL**](ns-iddcx-idarg_out_monitorarrival.md) structure in which to return details about the monitor that arrived.

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

An IDD must first call [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md) to obtain the [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object.

## -see-also

[**IDARG_OUT_MONITORARRIVAL**](ns-iddcx-idarg_out_monitorarrival.md)

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md)

[**IddCxMonitorDeparture**](nf-iddcx-iddcxmonitordeparture.md)
