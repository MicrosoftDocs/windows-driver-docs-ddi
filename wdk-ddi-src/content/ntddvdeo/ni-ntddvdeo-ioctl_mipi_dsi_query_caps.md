---
UID: NI:ntddvdeo.IOCTL_MIPI_DSI_QUERY_CAPS
title: IOCTL_MIPI_DSI_QUERY_CAPS
author: windows-driver-content
description: IOCTL_MIPI_DSI_QUERY_CAPS retrieves the basic capabilities of the MIPI DSI interface exposed by the graphics driver, and identification information from the panel.
tech.root: display
ms.assetid: 8472c449-74ee-4590-a94b-7d726e1707db
ms.author: windowsdriverdev
ms.date: 03/24/2020
f1_keywords:
 - "ntddvdeo/IOCTL_MIPI_DSI_QUERY_CAPS"
 - "IOCTL_MIPI_DSI_QUERY_CAPS"
req.header: ntddvdeo.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.max-support:
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddvdeo.h
api_name: 
 - IOCTL_MIPI_DSI_QUERY_CAPS
targetos: Windows
dev_langs:
 - c++
---

# IOCTL_MIPI_DSI_QUERY_CAPS IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

**IOCTL_MIPI_DSI_QUERY_CAPS** retrieves the basic capabilities of the MIPI DSI interface exposed by the graphics driver, and identification information from the panel.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

n/a

### -output-buffer

Buffer in which the DSI capabilities are returned. Must be at least ```sizeof(DXGK_DSI_CAPS)```.

### -output-buffer-length

Size in bytes of the output buffer.

### -in-out-buffer

n/a

### -inout-buffer-length

n/a

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Mobile Industry Processor Interface (MIPI) Digital Serial Interface(DSI) IOCTLs must be handled by the monitor, oem-panel, or port/miniport driver.

The OEM panel driver should initialize by using **IOCTL_MIPI_DSI_QUERY_CAPS** which provides information to allow the OEM panel driver to verify driver support and provides the raw level 1 DDB data from the display to allow one panel driver to support multiple devices and to confirm that there is no mismatch. The capabilities are returned in a [**DXGK_DSI_CAPS**](../dispmprt/ns-dispmprt-dxgk_dsi_caps.md) structure. It is responsibility of the OEM panel driver to validate DSI capability, and compatibility with the panel since neither the graphics driver nor the OS has sufficient information to do so, particularly for any manufacturer defined or undefined elements.

The OS translates the query IOCTL into a call to [**DsiQueryCaps**](../dispmprt/nc-dispmprt_dxgk_dsicaps.md), passing in the target id of the monitor as input and the caps structure for output. The graphics driver should fill in the requested fields, using cached information if available since the data should be static. Since the OS needs the **TargetMaximumReturnPacketSize** value for packet validation, it may request the capabilities from the graphics driver before receiving a request from the panel driver.

## -see-also

[**DsiQueryCaps**](../dispmprt/nc-dispmprt_dxgk_dsicaps.md)

[**DXGK_DSI_CAPS**](../dispmprt/ns-dispmprt-dxgk_dsi_caps.md)

[**IOCTL_MIPI_DSI_RESET**](ni-ntddvdeo-ioctl_mipi_dsi_reset.md)

[**IOCTL_MIPI_DSI_TRANSMISSION**](ni-ntddvdeo-ioctl_mipi_dsi_transmission.md)
