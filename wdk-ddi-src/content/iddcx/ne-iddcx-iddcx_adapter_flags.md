---
UID: NE:iddcx.IDDCX_ADAPTER_FLAGS
title: IDDCX_ADAPTER_FLAGS (iddcx.h)
description: Learn more about the IDDCX_ADAPTER_FLAGS enumeration.
tech.root: display
ms.date: 09/22/2023
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

### -field IDDCX_ADAPTER_FLAGS_USE_SMALLEST_MODE:0x1

The indirect display model automatically supports OS virtual modes, allowing the OS to seamlessly perform mode changes using Desktop Window Manager (DWM) scaling on a per frame basis without a display mode change. A disadvantage occurs when a smaller desktop mode is used by the user: the desktop image provided to the driver is larger than the desktop size, thus wasting encode and transmit bandwidth.

This enum value tells the OS to use the smallest possible desktop surface size when the desktop mode is changed. A solution that has large processing overhead or limited transmission bandwidth typically uses this flag to reduce the desktop image size in order to process as much as possible.

Setting this flag results in a mode change each time the desktop resolution is changed.

### -field IDDCX_ADAPTER_FLAGS_CAN_USE_MOVE_REGIONS:0x2

This flag was [deprecated starting in IddCx v1.7](/windows-hardware/drivers/display/iddcx1.7-updates). Drivers can still set this flag for IddCx 1.7 and above but it will have no effect. If a driver is designed to run on pre-IddCx 1.7 and sets this flag, that driver must have the logic to process the moves; otherwise users will see visual issues when running on pre-IddCx 1.7 systems.

Indicates whether the driver can use move regions provided by the OS in addition to dirty rects when encoding the image. The driver should only set this to TRUE if it uses the move regions because the OS incurs a cost when generating these additional resources. If driver sets this to FALSE, the OS converts all move regions to dirty rects.

### -field IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER:0x4

Indicates whether the driver is a remote session driver supporting remote session monitors, rather than console session monitors. A remote session driver cannot support console session monitors, and a console session driver cannot support remote session monitors. Supported starting in [IddCx version 1.4](/windows-hardware/drivers/display/iddcx1.4-updates).

### -field IDDCX_ADAPTER_FLAGS_PREFER_PHYSICALLY_CONTIGUOUS:0x8

Indicates that the driver prefers physically contiguous memory to be used for swap chain buffers, allowing the driver to directly scan out the buffers without the need for an intermediate copy. Supported starting in [IddCx version 1.6](/windows-hardware/drivers/display/iddcx1.6-updates).

### -field IDDCX_ADAPTER_FLAGS_REMOTE_ALL_CURSOR_POSITION:0x10

Indicates that the driver wants to receive all cursor position changes; that is, it wants to receive both mouse input injected into the remote session from the remote client and procedural moves caused by an API call from an application or the OS on the server.

This flag is only valid when combined with **IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER**. [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) will fail if **IDDCX_ADAPTER_FLAGS_REMOTE_ALL_CURSOR_POSITION** is set without **IDDCX_ADAPTER_FLAGS_REMOTE_SESSION_DRIVER**.

Supported starting in [IddCx version 1.7](/windows-hardware/drivers/display/iddcx1.7-updates).

### -field IDDCX_ADAPTER_FLAGS_PREFER_PRECISE_PRESENT_REGIONS:0x20

A driver that sets this flag is requesting the OS to track dirty regions of the desktop updates more accurately. This more accurate tracking has a small CPU usage overhead so drivers should only set this flag if smaller dirty regions are beneficial to the driver.

Supported starting in [IddCx version 1.8](/windows-hardware/drivers/display/iddcx1.8-updates).

### -field IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16: 0x40

Indicates that the driver can process IEEE half-precision floating point (FP16) swapchain surfaces. A driver should set **IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16** even for adapters that don't support HDR or SDR WCG. The OS sends HDR or SDR WC surfaces and modes to the driver when the right combination of monitor, target capabilities, O settings, and so forth are in place. Therefore, a driver that sets **IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16** must also support the IddCx version 1.10 functions that allow this to happen. A driver that supports HDR10 must be capable of:

* Receiving and processing FP16 format surfaces within a swapchain.
* Applying the indicated SDR white level to mouse cursors.

Console drivers must also:

* Use the new 3x4 matrix color transform.
* Accept and use HDR metadata.

Remote drivers must also:

* Supply colorimetry and SDR white level when required.

Supported starting in [IddCx version 1.10](/windows-hardware/drivers/display/iddcx1.10-updates). See Remarks.

### -field IDDCX_ADAPTER_FLAGS_REMOTE_ALL_TARGET_MODES_MONITOR_COMPATIBLE:0x80

Only remote drivers can set this flag.

Remote drivers can use **IDDCX_ADAPTER_FLAGS_ALL_TARGET_MODES_MONITOR_COMPATIBLE** to allow them to specify target modes that are not part of a monitor descriptor. Normally the OS chooses a mode based on it being in both the monitor and target mode list, reported either via [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**](nc-iddcx-evt_idd_cx_parse_monitor_description.md) or [**EVT_IDD_CX_MONITOR_GET_DEFAULT_DESCRIPTION_MODES**](nc-iddcx-evt_idd_cx_monitor_get_default_description_modes.md) if no descriptor is available, and the target mode list. Remote scenarios may require modes that are not in the descriptor. Instead, the driver can use target modes to describe them and indicate to the OS they should not be checked against monitor modes.

When a remote driver sets this flag, it indicates that every target mode reported in calls to [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md) and [**IddCxMonitorUpdateModes2**](f-iddcx-iddcxmonitorupdatemodes2.md) is guaranteed to be compatible with the currently connected monitor. The OS will then not call [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md) or [**EVT_IDD_CX_MONITOR_GET_DEFAULT_DESCRIPTION_MODES**](nc-iddcx-evt_idd_cx_monitor_get_default_description_modes.md).

Supported starting in [IddCx version 1.10](/windows-hardware/drivers/display/iddcx1.10-updates). See Remarks.

## -remarks

To determine whether the OS accepts drivers setting **IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16** or **IDDCX_ADAPTER_FLAGS_ALL_TARGET_MODES_MONITOR_COMPATIBLE**, the driver should use the **IDD_IS_FUNCTION_AVAILABLE** macro to check for the presence of one of the version 1.10 DDIs; for example ```IDD_IS_FUNCTION_AVAILABLE(IddCxSwapChainReleaseAndAcquireBuffer2)```. This macro evaluates to TRUE on a v1.10-supported OS and false otherwise. See [Updates for IddCx versions 1.10 and later](/windows-hardware/drivers/display/iddcx1.10-updates) for more information.

## -see-also

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)

[**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md)
