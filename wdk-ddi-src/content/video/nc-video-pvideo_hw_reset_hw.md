---
UID: NC:video.PVIDEO_HW_RESET_HW
title: PVIDEO_HW_RESET_HW
author: windows-driver-content
description: HwVidResetHw resets the adapter to character mode.
old-location: display\hwvidresethw.htm
tech.root: display
ms.assetid: dae00663-17bd-461d-9b3f-febff2d9811b
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: HwVidResetHw, HwVidResetHw callback function [Display Devices], PVIDEO_HW_RESET_HW, PVIDEO_HW_RESET_HW callback, VideoMiniport_Functions_783bcc9a-8af3-4cfb-8121-a2bbeb0e64f1.xml, display.hwvidresethw, video/HwVidResetHw
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidResetHw
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_RESET_HW callback function


## -description


<i>HwVidResetHw</i> resets the adapter to character mode.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Columns

Specifies the number of columns of the mode to be set up.


### -param Rows

Specifies the number of rows of the mode to be set up.


## -returns



<i>HwVidResetHw</i> should return <b>TRUE</b> if it completely resets the adapter to the given character mode. Otherwise, it should return <b>FALSE</b> to indicate that the HAL should perform the equivalent of an INT10, MODE3-type BIOS call after <i>HwVidResetHw</i> returns control.




## -remarks



A video miniport driver must have a <i>HwVidResetHw</i> function if its adapter cannot be reset to a fully initialized state without a hard boot of the machine. For example, if the adapter's ROM initialization code cannot reset the adapter state to a boot-up mode, the miniport driver must have a <i>HwVidResetHw</i> function. Another reason the miniport driver must implement this function is to clean up the adapter's interrupt lines when the adapter is powered down, thereby avoiding a deluge of interrupts the next time the system boots.

The HAL calls <i>HwVidResetHw</i> if the system is about to crash, so that the HAL can display information on the screen while the system is being shut down. This call can occur at any IRQL, and the driver must be ready to handle it at any time. The HAL also calls <i>HwVidResetHw</i> just before the machine is rebooted when a soft boot occurs.

Most miniport drivers must provide this function, except for drivers of adapters that are reset to a VGA standard character mode on receipt of an INT10, MODE3-type command.

<i>HwVidResetHw</i> resets the adapter to character mode, according to the given <i>Columns</i> and <i>Rows</i> values. However, because the system is shutting down, <i>HwVidResetHw</i> cannot call the BIOS or any pageable code. <i>HwVidResetHw</i> should call only the <b>VideoPortRead/WritePort</b><i>Xxx</i> and/or <b>VideoPortRead/WriteRegister</b><i>Xxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff566461">Functions Exported by the Video Port Driver</a>.)

If <i>HwVidResetHw</i> cannot change the mode of the adapter by simply programming the adapter registers, it can set up the appropriate values in adapter registers and return <b>FALSE</b>. This causes the HAL to perform an extended INT10-type operation to reset the video adapter to character mode.

<i>HwVidResetHw</i> must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570321">VideoPortInt10</a>. A miniport driver's <a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a> function is called with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567834">IOCTL_VIDEO_RESET_DEVICE</a><a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a> to reset the adapter whenever the Display program is used to test or change the graphics display mode, <i>not</i> the miniport driver's <i>HwVidResetHw</i> function.

<i>HwVidResetHw</i> must not be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566461">Functions Exported by the Video Port Driver</a>



<a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a>



<a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567834">IOCTL_VIDEO_RESET_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570321">VideoPortInt10</a>
 

 

