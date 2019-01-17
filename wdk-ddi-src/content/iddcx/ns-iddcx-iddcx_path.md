---
UID: NS:iddcx.IDDCX_PATH
title: IDDCX_PATH
description: Call IDDCX_PATH_INIT to initialize this structure.
old-location: display\iddcx_path.htm
tech.root: display
ms.assetid: c0126718-6bb0-493c-9fdd-78ae372f8fd4
ms.date: 05/10/2018
ms.keywords: IDDCX_PATH, IDDCX_PATH structure, IDDCX_PATH structure [Display Devices], IDDCX_PATH structure pointer [Display Devices], IDDCX_PATH structure structure [Display Devices], display.iddcx_path, iddcx/IDDCX_PATH
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
-	IDDCX_PATH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_PATH structure


## -description



                 Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt761937">IDDCX_PATH_INIT</a> to initialize this structure.
             


## -struct-fields




### -field Size


                     Total size of the structure.
                 


### -field MonitorObject


                     The handle the driver provides to identify the monitor this path is targeted at.
                 


### -field Flags


                     Contains flags for this path, like the path's active state and whether it changed.
                 


### -field TargetVideoSignalInfo

The details of the target mode signal. 
                 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b> is the Vsync rate between the Indirect Display device and the connected monitor.  <b>vSyncFreqDivider</b> is used to calculate the rate at which the OS will update the desktop image.

The desktop update rate will be calculated by the formula: <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b>  divided by the <b>DISPLAYCONFIG_VIDEO_SIGNAL_INFO</b> value <b>vSyncFreqDivider</b>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554007">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a>  value <b>vSyncFreqDivider</b> cannot be zero



