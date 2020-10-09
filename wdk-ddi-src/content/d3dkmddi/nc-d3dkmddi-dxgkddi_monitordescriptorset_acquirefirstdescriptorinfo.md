---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO
title: DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO (d3dkmddi.h)
description: The pfnAcquireFirstDescriptorInfo function returns the first descriptor in a monitor descriptor set object.
old-location: display\dxgk_monitordescriptorset_interface_pfnacquirefirstdescriptorinfo.htm
ms.assetid: 228f6947-a7e5-4b76-8224-fac6889fc77a
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO callback function"]
ms.keywords: DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO, DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO callback, VidPnFunctions_fae7b938-60d5-41c0-92a8-9381e67aa411.xml, d3dkmddi/pfnAcquireFirstDescriptorInfo, display.dxgk_monitordescriptorset_interface_pfnacquirefirstdescriptorinfo, pfnAcquireFirstDescriptorInfo, pfnAcquireFirstDescriptorInfo callback function [Display Devices]
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
 - DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO
 - d3dkmddi/DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireFirstDescriptorInfo
product:
 - Windows
---

# DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO callback function


## -description

The <b>pfnAcquireFirstDescriptorInfo</b> function returns the first descriptor in a monitor descriptor set object.

## -parameters

### -param hMonitorDescriptorSet

[in] A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function of the <a href="/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param ppFirstMonitorDescriptorInfo

[out] A pointer to a variable that receives a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_descriptor">D3DKMDT_MONITOR_DESCRIPTOR</a> structure. The structure is the first descriptor in the set.

## -returns

The <b>pfnAcquireFirstDescriptorInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully returned the first descriptor in the set.|
|STATUS_GRAPHICS_DATASET_IS_EMPTY|The function succeeded, but there were no descriptors in the set.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET|The handle supplied in *hMonitorDescriptorSet* was invalid.|

## -remarks

When you have finished using the D3DKMDT_MONITOR_DESCRIPTOR structure, you must release the structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo">pfnReleaseDescriptorInfo</a>.

You can obtain all the descriptors in a monitor descriptor set by calling <b>pfnAcquireFirstDescriptorInfo</b> and then making a sequence of calls to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo">pfnAcquireNextDescriptorInfo</a>.