---
UID: NS:ntifs._WIM_PROVIDER_SUSPEND_OVERLAY_INPUT
title: "_WIM_PROVIDER_SUSPEND_OVERLAY_INPUT"
author: windows-driver-content
description: A Windows Image File (WIM) data source to suspend from the WIM provider is specified in the WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_suspend_overlay_input.htm
old-project: ifsk
ms.assetid: 85BECD4F-3039-483F-8ED1-EFCA6BEE1181
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT, PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT, PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, ifsk.wim_provider_suspend_overlay_input, ntifs/PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT, ntifs/WIM_PROVIDER_SUSPEND_OVERLAY_INPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
-	ntifs.h
api_name:
-	WIM_PROVIDER_SUSPEND_OVERLAY_INPUT
product:
- Windows
targetos: Windows
req.typenames: WIM_PROVIDER_SUSPEND_OVERLAY_INPUT, *PWIM_PROVIDER_SUSPEND_OVERLAY_INPUT
---

# _WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure


## -description


A Windows Image File (WIM) data source to suspend from the WIM provider is specified in the <b>WIM_PROVIDER_SUSPEND_OVERLAY_INPUT</b> structure.


## -struct-fields




### -field DataSourceId

An identifier value for the WIM file data source to suspend.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn632442">FSCTL_REMOVE_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt426735">FSCTL_SUSPEND_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn632445">FSCTL_UPDATE_OVERLAY</a>
 

 

