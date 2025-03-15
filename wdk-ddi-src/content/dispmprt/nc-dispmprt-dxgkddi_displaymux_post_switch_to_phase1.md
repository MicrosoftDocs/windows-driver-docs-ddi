---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
tech.root: display
title: DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1 function.
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
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
f1_keywords:
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
 - dispmprt/DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_POST_SWITCH_TO_PHASE1
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxPostSwitchToPhase1** function to notify the driver that the mux switch has completed, and that the driver is now connected to the display and should perform phase 1 tasks.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param SwitchPrivateDataSize

[in] The size, in bytes, of the buffer that is pointed to by **pSwitchPrivateDataBuffer**.

### -param pSwitchPrivateDataBuffer

[in] A pointer to a buffer that contains the private data that was obtained from the GPU that the [mux was switched away from](nc-dispmprt-dxgkddi_displaymux_pre_switch_away_get_private_data.md)

### -param pSwitchPrivateDataGUID

[in] Pointer to the GUID that describes the version/layout of the private data.

## -returns

**DxgkddiDisplayMuxPostSwitchToPhase1** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

KMD needs to both verify that it understands the passed GUID and validate the integrity of the data in the buffer.

If KMD doesn't understand the packet, it should ignore it. In this situation, KMD shouldn't fail the call.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkddiDisplayMuxPostSwitchAway**](nc-dispmprt-dxgkddi_displaymux_post_switch_away.md)

[**DxgkddiDisplayMuxPostSwitchToPhase2**](nc-dispmprt-dxgkddi_displaymux_post_switch_to_phase2.md)

[**DxgkddiDisplayMuxPreSwitchAwayGetPrivateData**](nc-dispmprt-dxgkddi_displaymux_pre_switch_away_get_private_data.md)
