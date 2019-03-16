---
UID: NS:ntddvdeo._VIDEO_POWER_MANAGEMENT
title: _VIDEO_POWER_MANAGEMENT (ntddvdeo.h)
description: The VIDEO_POWER_MANAGEMENT structure contains information required by the miniport driver to perform power management.
old-location: display\video_power_management.htm
tech.root: display
ms.assetid: 9522c504-9bdb-4388-b047-340a211463dd
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_POWER_MANAGEMENT, PVIDEO_POWER_MANAGEMENT, PVIDEO_POWER_MANAGEMENT structure pointer [Display Devices], VIDEO_POWER_MANAGEMENT, VIDEO_POWER_MANAGEMENT structure [Display Devices], Video_Structs_d179543a-6712-4c33-a945-7bbf8a5bc1ed.xml, _VIDEO_POWER_MANAGEMENT, display.video_power_management, ntddvdeo/PVIDEO_POWER_MANAGEMENT, ntddvdeo/VIDEO_POWER_MANAGEMENT"
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- VIDEO_POWER_MANAGEMENT
product:
- Windows
targetos: Windows
req.typenames: VIDEO_POWER_MANAGEMENT, *PVIDEO_POWER_MANAGEMENT
---

# _VIDEO_POWER_MANAGEMENT structure


## -description


The VIDEO_POWER_MANAGEMENT structure contains information required by the miniport driver to perform power management.


## -struct-fields




### -field Length

Is the size in bytes of this VIDEO_POWER_MANAGEMENT structure.


### -field DPMSVersion

Specifies the version of the Display Power Management Signaling (DPMS) standard supported by the device. Currently, the video port driver sets this member to zero, which corresponds with Version 1.0 of the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VESA</a> DPMS Standard.


### -field PowerState

Specifies the power management state to be set or queried. This member can be one of the following values in the VIDEO_POWER_STATE enumeration:





#### VideoPowerOn

The monitor and graphics adapter are both fully powered on and operational.



#### VideoPowerStandBy

The monitor is running at a reduced power level that requires a short recovery time to <b>VideoPowerOn</b>. The graphics adapter is powered on (registers are still active and video memory is refreshed); however, clocks might be lost.



#### VideoPowerSuspend

The monitor is running at a substantially reduced power level that requires a possibly longer recovery time than <b>VideoPowerStandBy</b> to <b>VideoPowerOn</b>. The graphics adapter is off.



#### VideoPowerOff

The monitor and graphics adapter are both off, consuming no power at all.



#### VideoPowerHibernate

The monitor and graphics adapter are both fully powered on and operational.


## -remarks



The video port driver allocates and fills in the VIDEO_POWER_MANAGEMENT structure. Depending on the power management request dispatched to the video port, the video port driver passes this structure to the miniport driver's <a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a> or <a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a> routine.

<b>VideoPowerHibernate</b> is provided to the miniport driver as notification only. The miniport driver's <i>HwVidSetPowerState</i> function must leave the monitor and graphics adapter fully powered on and operational. For all other states, the miniport driver must put the device into the specified power state.

A driver will always enter all other power states from the <b>VideoPowerOn</b> state. For example, a driver will not move directly to <b>VideoPowerHibernate</b> from <b>VideoPowerOff</b>; it will always go from <b>VideoPowerHibernate</b> to <b>VideoPowerOn</b> and then to <b>VideoPowerOff</b>.




## -see-also




<a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a>



<a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a>
 

 

