---
UID: NS:ntifs._WIM_PROVIDER_REMOVE_OVERLAY_INPUT
title: _WIM_PROVIDER_REMOVE_OVERLAY_INPUT (ntifs.h)
description: A Windows Image File (WIM) data source to remove from the WIM provider is specified in the WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_remove_overlay_input.htm
tech.root: ifsk
ms.assetid: 8E228EA7-06ED-4BFB-AB15-E86334B9B0E8
ms.date: 04/16/2018
keywords: ["WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure"]
ms.keywords: "*PWIM_PROVIDER_REMOVE_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT structure [Installable File System Drivers], WIM_PROVIDER_REMOVE_OVERLAY_INPUT, WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_REMOVE_OVERLAY_INPUT, ifsk.wim_provider_remove_overlay_input, ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT, ntifs/WIM_PROVIDER_REMOVE_OVERLAY_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
req.typenames: WIM_PROVIDER_REMOVE_OVERLAY_INPUT, *PWIM_PROVIDER_REMOVE_OVERLAY_INPUT
f1_keywords:
 - _WIM_PROVIDER_REMOVE_OVERLAY_INPUT
 - ntifs/_WIM_PROVIDER_REMOVE_OVERLAY_INPUT
 - PWIM_PROVIDER_REMOVE_OVERLAY_INPUT
 - ntifs/PWIM_PROVIDER_REMOVE_OVERLAY_INPUT
 - WIM_PROVIDER_REMOVE_OVERLAY_INPUT
 - ntifs/WIM_PROVIDER_REMOVE_OVERLAY_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - WIM_PROVIDER_ADD_OVERLAY_INPUT
---

# _WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure


## -description

A Windows Image File (WIM) data source to remove from the WIM provider is specified in the <b>WIM_PROVIDER_REMOVE_OVERLAY_INPUT</b> structure.

## -struct-fields

### -field DataSourceId

An identifier value for the WIM file data source to remove.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-remove-overlay">FSCTL_REMOVE_OVERLAY</a> request contains a <b>WIM_PROVIDER_REMOVE_OVERLAY_INPUT</b>  in the system buffer as input. The value in <b>DataSourceId</b> is the data source identifier returned from a prior  <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-add-overlay">FSCTL_ADD_OVERLAY</a> control request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-add-overlay">FSCTL_ADD_OVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-remove-overlay">FSCTL_REMOVE_OVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-suspend-overlay">FSCTL_SUSPEND_OVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-update-overlay">FSCTL_UPDATE_OVERLAY</a>

