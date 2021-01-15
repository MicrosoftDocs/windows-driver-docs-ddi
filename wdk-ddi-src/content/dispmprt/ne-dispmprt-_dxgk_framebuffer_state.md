---
UID: NE:dispmprt._DXGK_FRAMEBUFFER_STATE
title: _DXGK_FRAMEBUFFER_STATE (dispmprt.h)
description: The frame buffer state is provided to the driver in order that the driver can infer details of the display configuration based on knowledge of how firmware and the driver will set a particular resolution even though only basic information is made directly available by the OS to the driver.
old-location: display\dxgk_framebuffer_state.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_FRAMEBUFFER_STATE enumeration"]
ms.keywords: DXGK_FRAMEBUFFER_STATE, DXGK_FRAMEBUFFER_STATE enumeration [Display Devices], FrameBufferStateInitializedByDriver, FrameBufferStateInitializedByFirmware, FrameBufferStateUnknown, _DXGK_FRAMEBUFFER_STATE, display.dxgk_framebuffer_state, dispmprt/DXGK_FRAMEBUFFER_STATE, dispmprt/FrameBufferStateInitializedByDriver, dispmprt/FrameBufferStateInitializedByFirmware, dispmprt/FrameBufferStateUnknown
req.header: dispmprt.h
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
req.typenames: DXGK_FRAMEBUFFER_STATE
f1_keywords:
 - _DXGK_FRAMEBUFFER_STATE
 - dispmprt/_DXGK_FRAMEBUFFER_STATE
 - DXGK_FRAMEBUFFER_STATE
 - dispmprt/DXGK_FRAMEBUFFER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_FRAMEBUFFER_STATE
 - DXGK_FRAMEBUFFER_STATE
---

# _DXGK_FRAMEBUFFER_STATE enumeration


## -description

The frame buffer state is provided to the driver in order that the driver can infer details of the display configuration based on knowledge of how firmware and the driver will set a particular resolution even though only basic information is made directly available by the OS to the driver.

## -enum-fields

### -field FrameBufferStateUnknown

Value indicating that the OS has insufficient information to report the frame buffer state.

### -field FrameBufferStateInitializedByFirmware

Value indicating that the frame buffer was initialized using either UEFI or VBIOS.

### -field FrameBufferStateInitializedByDriver

Value indicating that the hardware specific driver last initialized the frame buffer when the previous driver was stopped.  Note, the driver which initialized the frame buffer may not be the same version as is currently running if the driver has been updated.

## -remarks

FrameBufferStateUnknown will be reported if the frame buffer state is undefined, or if the frame buffer has been initialized but may have been changed by the Basic Display Driver.  The other two states should only be reported if that state is reliable.

