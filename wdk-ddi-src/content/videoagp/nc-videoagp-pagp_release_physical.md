---
UID: NC:videoagp.PAGP_RELEASE_PHYSICAL
title: PAGP_RELEASE_PHYSICAL
author: windows-driver-content
description: The AgpReleasePhysical function frees a physical address range reserved by a previous call to AgpReservePhysical.
old-location: display\agpreleasephysical.htm
tech.root: display
ms.assetid: 4da0f5cb-a017-4df5-958b-c76b7a08495a
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: AgpReleasePhysical, AgpReleasePhysical callback function [Display Devices], PAGP_RELEASE_PHYSICAL, PAGP_RELEASE_PHYSICAL callback, VideoPort_Functions_427923a7-3205-41a7-a470-dbc7d531e47f.xml, display.agpreleasephysical, videoagp/AgpReleasePhysical
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	videoagp.h
api_name:
-	AgpReleasePhysical
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_RELEASE_PHYSICAL callback function


## -description


The <b>AgpReleasePhysical</b> function frees a physical address range reserved by a previous call to <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param PhysicalReserveContext [in]

Is the context handle that identifies the reserved physical address range to be released. This context was obtained from <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>.


## -returns



None




## -remarks



The miniport driver must call <a href="https://msdn.microsoft.com/bb0e3330-5601-47dd-afc6-94a70b42daaf">AgpFreePhysical</a> to unmap all committed memory within the address range identified by <b>PhysicalReserveContext</b> before calling <b>AgpReleasePhysical</b>.




## -see-also




<a href="https://msdn.microsoft.com/bb0e3330-5601-47dd-afc6-94a70b42daaf">AgpFreePhysical</a>



<a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>
 

 

