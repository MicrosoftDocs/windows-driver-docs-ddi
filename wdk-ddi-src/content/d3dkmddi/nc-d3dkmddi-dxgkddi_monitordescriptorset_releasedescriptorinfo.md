---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO
title: DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO
author: windows-driver-content
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnReleaseDescriptorInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO callback function


## -description


The <b>pfnReleaseDescriptorInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546087">D3DKMDT_MONITOR_DESCRIPTOR</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hMonitorDescriptorSet [in]

A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/e2244cd3-6630-440b-a4f7-1e0fa5702161">pfnGetMonitorDescriptorSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorDescriptorInfo [in]

A pointer to the D3DKMDT_MONITOR_DESCRIPTOR structure to be released.


## -returns



The <b>pfnReleaseDescriptorInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_MONITOR_DESCRIPTOR|The descriptor supplied in pMonitorDescriptorInfo was invalid.|
|STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET|The handle supplied in hMonitorDescriptorSet was invalid.|
 




## -remarks



When you have finished using a D3DKMDT_MONITOR_DESCRIPTOR structure that you obtained by calling <a href="https://msdn.microsoft.com/228f6947-a7e5-4b76-8224-fac6889fc77a">pfnAcquireFirstDescriptorInfo</a> or <a href="https://msdn.microsoft.com/34d048df-d4a1-4ef5-b917-791f35de9e3a">pfnAcquireNextDescriptorInfo</a>, you must release it by calling <b>pfnReleaseDescriptorInfo</b>.



