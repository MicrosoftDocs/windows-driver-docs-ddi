---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE_V2
title: "_DXGK_MONITOR_INTERFACE_V2"
author: windows-driver-content
description: The DXGK_MONITOR_INTERFACE_V2 structure, available beginning with Windows 7, contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitor_interface_v2.htm
old-project: display
ms.assetid: 5c08b988-2cc0-46e1-a8b5-66de840650e4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_MONITOR_INTERFACE_V2, DXGK_MONITOR_INTERFACE_V2 structure [Display Devices], DmStructs_8af61532-16df-472d-abb7-c8f9a677e968.xml, _DXGK_MONITOR_INTERFACE_V2, d3dkmddi/DXGK_MONITOR_INTERFACE_V2, display.dxgk_monitor_interface_v2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MONITOR_INTERFACE_V2
product: Windows
targetos: Windows
req.typenames: DXGK_MONITOR_INTERFACE_V2
---

# _DXGK_MONITOR_INTERFACE_V2 structure


## -description


The DXGK_MONITOR_INTERFACE_V2 structure, available beginning with Windows 7, contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>, which is implemented by the video present network (VidPN) manager.


## -syntax


````
typedef struct _DXGK_MONITOR_INTERFACE_V2 {
  DXGK_MONITOR_INTERFACE_VERSION                  Version;
  DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET     pfnAcquireMonitorSourceModeSet;
  DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET     pfnReleaseMonitorSourceModeSet;
  DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET     pfnGetMonitorFrequencyRangeSet;
  DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET         pfnGetMonitorDescriptorSet;
  DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET     pfnGetAdditionalMonitorModeSet;
  DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET pfnReleaseAdditionalMonitorModeSet;
} DXGK_MONITOR_INTERFACE_V2;
````


## -struct-fields




### -field Version

A value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_monitor_interface_version.md">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that indicates the monitor interface version. Must be set to 2.


### -field pfnAcquireMonitorSourceModeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function.


### -field pfnReleaseMonitorSourceModeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset.md">pfnReleaseMonitorSourceModeSet</a> function.


### -field pfnGetMonitorFrequencyRangeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md">pfnGetMonitorFrequencyRangeSet</a> function.


### -field pfnGetMonitorDescriptorSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md">pfnGetMonitorDescriptorSet</a> function.


### -field pfnGetAdditionalMonitorModeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">pfnGetAdditionalMonitorModeSet</a> function.


### -field pfnReleaseAdditionalMonitorModeSet


      A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md">pfnReleaseAdditionalMonitorModeSet</a> function.
     


## -remarks



<div class="alert"><b>Note</b>    A display miniport driver must verify the interface version specified in the <b>Version</b> member before using this structure. This structure is available beginning with Windows 7.</div>
<div> </div>



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface.md">DXGK_MONITOR_INTERFACE</a>



 

 


