---
UID: NE:d3dkmddi._DXGK_MONITOR_INTERFACE_VERSION
title: "_DXGK_MONITOR_INTERFACE_VERSION"
author: windows-driver-content
description: Indicates a particular version of the Monitor interface.
old-location: display\dxgk_monitor_interface_version.htm
old-project: display
ms.assetid: 76af0d70-f9bb-4768-9bfd-f2aaeb212db0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, DmEnums_4ec3a10c-c04f-431b-851d-908a5ff972a1.xml, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION, DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, display.dxgk_monitor_interface_version, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V1, DXGK_MONITOR_INTERFACE_VERSION, DXGK_MONITOR_INTERFACE_VERSION_V2, _DXGK_MONITOR_INTERFACE_VERSION, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V2, DXGK_MONITOR_INTERFACE_VERSION enumeration [Display Devices], DXGK_MONITOR_INTERFACE_VERSION_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MONITOR_INTERFACE_VERSION
product: Windows
targetos: Windows
req.typenames: DXGK_MONITOR_INTERFACE_VERSION
---

# _DXGK_MONITOR_INTERFACE_VERSION enumeration


## -description


The <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration indicates a particular version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


## -syntax


````
typedef enum _DXGK_MONITOR_INTERFACE_VERSION { 
  DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED  = 0,
  DXGK_MONITOR_INTERFACE_VERSION_V1             = 1,
  DXGK_MONITOR_INTERFACE_VERSION_V2             = 2
} DXGK_MONITOR_INTERFACE_VERSION;
````


## -enum-fields




### -field DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED

Indicates that a variable of type DXGK_MONITOR_INTERFACE_VERSION has not yet been assigned a meaningful value.


### -field DXGK_MONITOR_INTERFACE_VERSION_V1

Indicates version 1, available in Windows Vista and later versions of the Windows operating systems.


### -field DXGK_MONITOR_INTERFACE_VERSION_V2


      Indicates version 2, available in Windows 7 and later versions of the Windows operating systems.
     


## -remarks


The <b>Version</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface.md">DXGK_MONITOR_INTERFACE</a> structure is a value from the <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration.


