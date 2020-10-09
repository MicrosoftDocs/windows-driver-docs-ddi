---
UID: NC:hdaudio.PGET_WALL_CLOCK_REGISTER
title: PGET_WALL_CLOCK_REGISTER (hdaudio.h)
description: The GetWallClockRegister routine retrieves a pointer to the wall clock register.The function pointer type for a GetWallClockRegister routine is defined as follows.
old-location: audio\getwallclockregister.htm
tech.root: audio
ms.assetid: 4efe4b23-eb4f-4170-8d73-05cae2ba21c2
ms.date: 05/08/2018
keywords: ["PGET_WALL_CLOCK_REGISTER callback function"]
ms.keywords: GetWallClockRegister, GetWallClockRegister callback function [Audio Devices], PGET_WALL_CLOCK_REGISTER, PGET_WALL_CLOCK_REGISTER callback, aud-prop2_1600e03f-4be0-4a61-9596-7970ace3df2f.xml, audio.getwallclockregister, hdaudio/GetWallClockRegister
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PGET_WALL_CLOCK_REGISTER
 - hdaudio/PGET_WALL_CLOCK_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - GetWallClockRegister
---

# PGET_WALL_CLOCK_REGISTER callback function


## -description

The <code>GetWallClockRegister</code> routine retrieves a pointer to the wall clock register.

The function pointer type for a <code>GetWallClockRegister</code> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

### -param Wallclock 

[out]
Retrieves a pointer to the wall clock register. This parameter points to a caller-allocated PULONG variable into which the routine writes a pointer to the register. The HD Audio bus driver maps the register to a system virtual address that is accessible to the function driver.

## -remarks

For more information, see <a href="/windows-hardware/drivers/audio/wall-clock-and-link-position-registers">Wall Clock and Link Position Registers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>