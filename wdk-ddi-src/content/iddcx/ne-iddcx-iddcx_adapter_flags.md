---
UID: NE:iddcx.IDDCX_ADAPTER_FLAGS
title: IDDCX_ADAPTER_FLAGS (iddcx.h)
description: Specifies boolean flags for an indirect display adapter.
old-location: display\iddcx_adapter_flags.htm
tech.root: display
ms.date: 10/20/2020
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

**IDDCX_ADAPTER_FLAGS** specifies the boolean capability flags of an indirect display adapter.

## -enum-fields

### -field IDDCX_ADAPTER_FLAGS_NONE

Indicates that there are no flags set for the adapter.

### -field IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE

The indirect display model automatically supports OS virtual modes, allowing the OS to seamlessly perform mode changes using Desktop Window Manager (DWM) scaling on a per frame basis without a display mode change. The disadvantage is that when a smaller desktop mode is used the the user, the desktop image provided to the driver will be bigger than the desktop size. This wastes encode and transmit bandwidth.

**IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE** indicates to the OS that the smallest possible desktop surface size should be used when the desktop mode is changed. A solution that has large processing overhead or limited transmission bandwidth typically uses this flag to reduce the desktop image size in order to process as much as possible.

> [!NOTE]
> Setting this flag results in a mode change each time the desktop resolution is changed.

### -field IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS

Indicates whether the driver can use move regions provided by the OS in addition to dirty rects when encoding the image. The driver should only set this to TRUE if it uses the move regions because the OS incurs a cost when generating these additional resources. If driver sets this to FALSE, the OS converts all move regions to dirty rects.

### -field IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER

Indicates whether the driver is a remote session driver supporting remote session monitors, rather than console session monitors. A remote session driver cannot support console session monitors, and console session driver cannot support remote session monitors.

Supported starting in IddCx version 1.4.

### -field IDDCX_ADAPTER_FLAGS_PREFER_PHYSICALLY_CONTIGUOUS

Indicates that the driver prefers physically contiguous memory to be used for swap chain buffers, allowing the driver to directly scan out the buffers without the need for an intermediate copy.

Supported starting in IddCx version 1.6.

### -field UINT

## -see also

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)
