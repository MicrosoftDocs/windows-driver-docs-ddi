---
UID: NS:d3dkmddi._DXGK_VIDPNTOPOLOGY_INTERFACE
title: "_DXGK_VIDPNTOPOLOGY_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the VidPn Topology interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpntopology_interface.htm
ms.assetid: 293103cc-217c-4dcb-82c1-971adba564a0
ms.date: 5/10/2018
ms.keywords: DXGK_VIDPNTOPOLOGY_INTERFACE, DXGK_VIDPNTOPOLOGY_INTERFACE structure [Display Devices], DmStructs_6e2f92a1-beaa-4485-bb27-aff719a693b4.xml, _DXGK_VIDPNTOPOLOGY_INTERFACE, d3dkmddi/DXGK_VIDPNTOPOLOGY_INTERFACE, display.dxgk_vidpntopology_interface
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
-	DXGK_VIDPNTOPOLOGY_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPNTOPOLOGY_INTERFACE
---

# _DXGK_VIDPNTOPOLOGY_INTERFACE structure


## -description


The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPn Topology interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumPaths

A pointer to the <a href="https://msdn.microsoft.com/60960774-3f90-4eeb-a408-fa37122f22ea">pfnGetNumPaths</a> function.


### -field pfnGetNumPathsFromSource

A pointer to the <a href="https://msdn.microsoft.com/6c5ee84d-e106-47fc-88bd-b184e9cdd561">pfnGetNumPathsFromSource</a> function.


### -field pfnEnumPathTargetsFromSource

A pointer to the <a href="https://msdn.microsoft.com/ca925b3c-8141-419d-99a1-43764ec07315">pfnEnumPathTargetsFromSource</a> function.


### -field pfnGetPathSourceFromTarget

A pointer to the <a href="https://msdn.microsoft.com/c3e7b025-2382-4a81-8d78-9333b62b556a">pfnGetPathSourceFromTarget</a> function.


### -field pfnAcquirePathInfo

A pointer to the <a href="https://msdn.microsoft.com/27a03106-a5b5-489c-968a-81b3ea9940cb">pfnAcquirePathInfo</a> function.


### -field pfnAcquireFirstPathInfo

A pointer to the <a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a> function.


### -field pfnAcquireNextPathInfo

A pointer to the <a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a> function.


### -field pfnUpdatePathSupportInfo

A pointer to the <a href="https://msdn.microsoft.com/affe9ab2-49ef-4284-b441-49c311158827">pfnUpdatePathSupportInfo</a> function.


### -field pfnReleasePathInfo

A pointer to the <a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a> function.


### -field pfnCreateNewPathInfo

A pointer to the <a href="https://msdn.microsoft.com/2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d">pfnCreateNewPathInfo</a> function.


### -field pfnAddPath


      A pointer to the <a href="https://msdn.microsoft.com/893e0be1-aa29-429a-a3ca-a9f19053fd92">pfnAddPath</a> function.
     


### -field pfnRemovePath

A pointer to the <a href="https://msdn.microsoft.com/463973e0-c443-417a-86ff-0b78773d40cc">pfnRemovePath</a> function.


## -remarks



The display miniport driver calls the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN topology object and a pointer to a DXGK_VIDPNTOPOLOGY_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN topology object.



