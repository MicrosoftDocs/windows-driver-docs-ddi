---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO
title: DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO (d3dkmddi.h)
description: The pfnReleaseDescriptorInfo function releases a D3DKMDT_MONITOR_DESCRIPTOR structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitordescriptorset_interface_pfnreleasedescriptorinfo.htm
ms.assetid: 8debdd01-c4e4-4b7c-b4cd-c1143ea7ebaa
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO, DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO callback, VidPnFunctions_6cc74bb6-8861-42b7-b877-634e042a4107.xml, d3dkmddi/pfnReleaseDescriptorInfo, display.dxgk_monitordescriptorset_interface_pfnreleasedescriptorinfo, pfnReleaseDescriptorInfo, pfnReleaseDescriptorInfo callback function [Display Devices]
ms.topic: callback
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
 - "d3dkmddi/pfnReleaseDescriptorInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnReleaseDescriptorInfo
product:
 - Windows
---

# DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO callback function

## -description

The <b>pfnReleaseDescriptorInfo</b> function releases a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_descriptor">D3DKMDT_MONITOR_DESCRIPTOR</a> structure that the VidPN manager previously provided to the display miniport driver.

## -parameters

### -param hMonitorDescriptorSet

A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor interface</a>.

### -param pMonitorDescriptorInfo

A pointer to the D3DKMDT_MONITOR_DESCRIPTOR structure to be released.

## -returns

The <b>pfnReleaseDescriptorInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_MONITOR_DESCRIPTOR|The descriptor supplied in pMonitorDescriptorInfo was invalid.|
|STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET|The handle supplied in hMonitorDescriptorSet was invalid.|

## -remarks

When you have finished using a D3DKMDT_MONITOR_DESCRIPTOR structure that you obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo">pfnAcquireFirstDescriptorInfo</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo">pfnAcquireNextDescriptorInfo</a>, you must release it by calling <b>pfnReleaseDescriptorInfo</b>.

