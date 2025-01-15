---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
tech.root: display
title: DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_REPORT_PRESENCE function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
f1_keywords:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
 - dispmprt/DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxReportPresence** function before adapter start to inform the driver that an automatic display switch (ADS) mux has been detected.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param SystemHasMux

[in] Boolean value that indicates whether the system has an ADS-compatible mux.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

**SystemHasMux** is set to TRUE when an ADS mux device was detected in the system and that mux device meets the ADS requirements. A TRUE value doesn't guarantee that ADS functionality will be available to user at this point in the boot sequence for the following reasons:

* The other GPU involved with the ADS mux might not be started yet.
* The OS has not yet verified all the ADS requirements for this driver.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).
