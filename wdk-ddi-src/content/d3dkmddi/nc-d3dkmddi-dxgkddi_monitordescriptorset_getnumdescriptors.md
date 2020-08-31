---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS
title: DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS (d3dkmddi.h)
description: The pfnGetNumDescriptors function returns the number of descriptors in a monitor descriptor set.
old-location: display\dxgk_monitordescriptorset_interface_pfngetnumdescriptors.htm
ms.assetid: 7bfcef0b-1371-4e3b-b5dc-c4c548625c8f
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS callback function"]
ms.keywords: DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS, DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS callback, VidPnFunctions_c2c4ad34-be07-4bd8-8576-e91b4549ca95.xml, d3dkmddi/pfnGetNumDescriptors, display.dxgk_monitordescriptorset_interface_pfngetnumdescriptors, pfnGetNumDescriptors, pfnGetNumDescriptors callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS
 - d3dkmddi/DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnGetNumDescriptors
product:
 - Windows
---

# DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS callback function


## -description

The <b>pfnGetNumDescriptors</b> function returns the number of descriptors in a monitor descriptor set.

## -parameters

### -param hMonitorDescriptorSet

[in] A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param pNumMonitorDescriptors

[out] A SIZE_T-typed variable that receives the number of descriptors in the set.

## -returns

The <b>pfnGetNumDescriptors</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET|The handle supplied in hMonitorDescriptorSet was invalid.|

