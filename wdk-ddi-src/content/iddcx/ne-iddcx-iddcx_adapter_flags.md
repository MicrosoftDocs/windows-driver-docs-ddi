---
UID: NE:iddcx.IDDCX_ADAPTER_FLAGS
title: IDDCX_ADAPTER_FLAGS (iddcx.h)
description: Specifies boolean flags for an indirect display adapter.
old-location: display\iddcx_adapter_flags.htm
tech.root: display
ms.date: 08/09/2022
keywords: ["IDDCX_ADAPTER_FLAGS enumeration"]
ms.keywords: IDDCX_ADAPTER_FLAGS, IDDCX_ADAPTER_FLAGS enumeration [Display Devices], IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS, IDDCX_ADAPTER_FLAGS_NONE, IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE, display.iddcx_adapter_flags, iddcx/IDDCX_ADAPTER_FLAGS, iddcx/IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS, iddcx/IDDCX_ADAPTER_FLAGS_NONE, iddcx/IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE
req.header: iddcx.h
req.include-header: 
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
ms.custom: 19H1
f1_keywords:
 - IDDCX_ADAPTER_FLAGS
 - iddcx/IDDCX_ADAPTER_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_ADAPTER_FLAGS
dev_langs:
 - c++
---

# IDDCX_ADAPTER_FLAGS enumeration

## -description

**IDDCX_ADAPTER_FLAGS** specifies the Boolean capability flags for an indirect display adapter.

## -enum-fields

### -field IDDCX_ADAPTER_FLAGS_NONE:0

Indicates that there are no flags set for the adapter.

### -field IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE:1

The indirect display model automatically supports OS virtual modes, allowing the OS to seamlessly perform mode changes using Desktop Window Manager (DWM) scaling on a per frame basis without a display mode change. The disadvantage is that when a smaller desktop mode is used by the user, the desktop image provided to the driver will be bigger than the desktop size, thus wasting encode and transmit bandwidth.

This enum value indicates to the OS that the smallest possible desktop surface size should be used when the desktop mode is changed. A solution that has large processing overhead or limited transmission bandwidth typically uses this flag to reduce the desktop image size in order to process as much as possible.

> [!NOTE]
> Setting this flag results in a mode change each time the desktop resolution is changed.

### -field IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS:2

This flag was [deprecated starting in IddCx v1.7](/windows-hardware/drivers/display/iddcx1.7-updates). Drivers can still set this flag for IddCx 1.7 and above but it will have no effect. If a driver is designed to run on pre-IddCx 1.7 and sets this flag, that driver must have the logic to process the moves; otherwise users will see visual issues when running on pre-IddCx 1.7 systems.

Indicates whether the driver can use move regions provided by the OS in addition to dirty rects when encoding the image. The driver should only set this to TRUE if it uses the move regions because the OS incurs a cost when generating these additional resources. If driver sets this to FALSE, the OS converts all move regions to dirty rects.

### -field IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER:4

Indicates whether the driver is a remote session driver supporting remote session monitors, rather than console session monitors. A remote session driver cannot support console session monitors, and a console session driver cannot support remote session monitors. Supported starting in IddCx version 1.4.

### -field IDDCX_ADAPTER_FLAGS_PREFER_PHYSICALLY_CONTIGUOUS:8

Indicates that the driver prefers physically contiguous memory to be used for swap chain buffers, allowing the driver to directly scan out the buffers without the need for an intermediate copy. Supported starting in IddCx version 1.6.

### -field IDDCX_ADAPTER_FLAGS_REMOTE_ALL_CURSOR_POSITION:16

Indicates that the driver wants to receive all cursor position changes; that is, it wants to receive both mouse input injected into the remote session from the remote client and procedural moves caused by an API call from an application or the OS on the server.

This flag is only valid when combined with **IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER**. [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) will fail if **IDDCX_ADAPTER_FLAGS_REMOTE_ALL_CURSOR_POSITION** is set without **IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER**.

Supported starting in IddCx version 1.7.

### -field IDDCX_ADAPTER_FLAGS_PREFER_PRECISE_PRESENT_REGIONS:32

A driver that sets this flag is requesting the OS to track dirty regions of the desktop updates more accurately. This more accurate tracking will have a small CPU usage overhead so drivers should only set this flag if smaller dirty regions will be beneficial to the driver.

Supported starting in IddCx version 1.8.

## -see-also

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)
