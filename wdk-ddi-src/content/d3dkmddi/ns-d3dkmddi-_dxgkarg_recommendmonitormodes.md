---
UID: NS:d3dkmddi._DXGKARG_RECOMMENDMONITORMODES
title: "_DXGKARG_RECOMMENDMONITORMODES"
author: windows-driver-content
description: The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the DxgkDdiRecommendMonitorModes function.
old-location: display\dxgkarg_recommendmonitormodes.htm
ms.assetid: 283f398e-4162-4c46-847b-834f8f303052
ms.date: 5/10/2018
ms.keywords: DXGKARG_RECOMMENDMONITORMODES, DXGKARG_RECOMMENDMONITORMODES structure [Display Devices], DmStructs_151c48fa-735a-4962-9fe7-446830441f1c.xml, _DXGKARG_RECOMMENDMONITORMODES, d3dkmddi/DXGKARG_RECOMMENDMONITORMODES, display.dxgkarg_recommendmonitormodes
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmddi.h
api_name:
-	DXGKARG_RECOMMENDMONITORMODES
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_RECOMMENDMONITORMODES
---

# _DXGKARG_RECOMMENDMONITORMODES structure


## -description


The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the <a href="https://msdn.microsoft.com/1fa29ab6-1faa-4be6-ae87-4cac9057471d">DxgkDdiRecommendMonitorModes</a> function. 


## -struct-fields




### -field VideoPresentTargetId

An integer that identifies a video present target on the display adapter.


### -field hMonitorSourceModeSet

A handle to a monitor source mode set object. This set contains a list of modes that are supported by the monitor that is connected to the video present target identified by <i>VideoPresentTargetId</i>.


### -field pMonitorSourceModeSetInterface

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561921">DXGK_MONITORSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can use to inspect, and possibly add modes to, the monitor source mode set.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561921">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/1fa29ab6-1faa-4be6-ae87-4cac9057471d">DxgkDdiRecommendMonitorModes</a>
 

 

