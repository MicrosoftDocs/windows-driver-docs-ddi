---
UID: NS:iddcx.IDDCX_TARGET_MODE
title: IDDCX_TARGET_MODE (iddcx.h)
description: Gives information about the target mode signal, including the bandwidth needed for the mode.
old-location: display\iddcx_target_mode.htm
tech.root: display
ms.assetid: 10bb23fa-ff1e-4bda-ba64-59a19da5f87e
ms.date: 05/10/2018
ms.keywords: IDDCX_TARGET_MODE, IDDCX_TARGET_MODE structure [Display Devices], display.iddcx_target_mode, iddcx/IDDCX_TARGET_MODE
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_TARGET_MODE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_TARGET_MODE structure


## -description



                 Gives information about the target mode signal, including the bandwidth needed for the mode.
             


## -struct-fields




### -field Size


                     Total size of the structure.
                 


### -field TargetVideoSignalInfo

The details of the target mode signal. 
                 


### -field RequiredBandwidth

The display pipeline bandwidth required for this mode.
                 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b> is the Vsync rate between the Indirect Display device and the connected monitor.  <b>vSyncFreqDivider</b> is used to calculate the rate at which the OS will update the desktop image.

The desktop update rate will be calculated by the formula: <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b>  divided by the <b>DISPLAYCONFIG_VIDEO_SIGNAL_INFO</b> value <b>vSyncFreqDivider</b>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a>  value <b>vSyncFreqDivider</b> cannot be zero



