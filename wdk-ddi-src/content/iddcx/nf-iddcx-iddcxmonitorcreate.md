---
UID: NF:iddcx.IddCxMonitorCreate
title: IddCxMonitorCreate function (iddcx.h)
description: An OS callback function the driver calls to create a monitor object that can later be used for arrival.
old-location: display\iddcxmonitorcreate.htm
tech.root: display
ms.date: 01/11/2021
keywords: ["IddCxMonitorCreate function"]
ms.keywords: IddCxMonitorCreate, IddCxMonitorCreate method [Display Devices], display.iddcxmonitorcreate, iddcx/IddCxMonitorCreate
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxMonitorCreate
 - iddcx/IddCxMonitorCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxMonitorCreate
---

# IddCxMonitorCreate function

## -description

An indirect display driver (IDD) calls **IddCxMonitorCreate** to create a monitor object that can later be used for arrival.

## -parameters

### -param AdapterObject

[in] The [IDDCX_ADAPTER](/windows-hardware/drivers/display/iddcx-objects) object that is hosting the newly arrived monitor.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_MONITORCREATE**](ns-iddcx-idarg_in_monitorcreate.md) structure containing information about the monitor.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_MONITORCREATE**](ns-iddcx-idarg_out_monitorcreate.md) structure in which the [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object is returned.

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

An IDD must call [**IddCxMonitorArrival**](nf-iddcx-iddcxmonitorarrival.md) to complete the monitor arrival.

## -see-also

[**IDARG_IN_MONITORCREATE**](ns-iddcx-idarg_in_monitorcreate.md)

[**IDARG_OUT_MONITORCREATE**](ns-iddcx-idarg_out_monitorcreate.md)

[**IddCxMonitorArrival**](nf-iddcx-iddcxmonitorarrival.md)
