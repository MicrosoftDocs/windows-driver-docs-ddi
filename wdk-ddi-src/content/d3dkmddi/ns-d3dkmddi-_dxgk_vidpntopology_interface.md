---
UID: NS:d3dkmddi._DXGK_VIDPNTOPOLOGY_INTERFACE
title: _DXGK_VIDPNTOPOLOGY_INTERFACE (d3dkmddi.h)
description: The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the VidPn Topology interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpntopology_interface.htm
ms.date: 10/30/2018
keywords: ["DXGK_VIDPNTOPOLOGY_INTERFACE structure"]
ms.keywords: DXGK_VIDPNTOPOLOGY_INTERFACE, DXGK_VIDPNTOPOLOGY_INTERFACE structure [Display Devices], DmStructs_6e2f92a1-beaa-4485-bb27-aff719a693b4.xml, _DXGK_VIDPNTOPOLOGY_INTERFACE, d3dkmddi/DXGK_VIDPNTOPOLOGY_INTERFACE, display.dxgk_vidpntopology_interface
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
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPNTOPOLOGY_INTERFACE
f1_keywords:
 - _DXGK_VIDPNTOPOLOGY_INTERFACE
 - d3dkmddi/_DXGK_VIDPNTOPOLOGY_INTERFACE
 - DXGK_VIDPNTOPOLOGY_INTERFACE
 - d3dkmddi/DXGK_VIDPNTOPOLOGY_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VIDPNTOPOLOGY_INTERFACE
 - DXGK_VIDPNTOPOLOGY_INTERFACE
---

# _DXGK_VIDPNTOPOLOGY_INTERFACE structure


## -description

The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the VidPn Topology interface, which is implemented by the video present network (VidPN) manager. For more info, see [VidPN Objects and Interfaces](/windows-hardware/drivers/display/vidpn-objects-and-interfaces).

## -struct-fields

### -field pfnGetNumPaths

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getnumpaths">pfnGetNumPaths</a> function.

### -field pfnGetNumPathsFromSource

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource">pfnGetNumPathsFromSource</a> function.

### -field pfnEnumPathTargetsFromSource

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_enumpathtargetsfromsource">pfnEnumPathTargetsFromSource</a> function.

### -field pfnGetPathSourceFromTarget

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getpathsourcefromtarget">pfnGetPathSourceFromTarget</a> function.

### -field pfnAcquirePathInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo">pfnAcquirePathInfo</a> function.

### -field pfnAcquireFirstPathInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo">pfnAcquireFirstPathInfo</a> function.

### -field pfnAcquireNextPathInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo">pfnAcquireNextPathInfo</a> function.

### -field pfnUpdatePathSupportInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_updatepathsupportinfo">pfnUpdatePathSupportInfo</a> function.

### -field pfnReleasePathInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a> function.

### -field pfnCreateNewPathInfo

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo">pfnCreateNewPathInfo</a> function.

### -field pfnAddPath

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_addpath">pfnAddPath</a> function.

### -field pfnRemovePath

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_removepath">pfnRemovePath</a> function.

## -remarks

The display miniport driver calls the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the VidPn interface to obtain a handle to a VidPN topology object and a pointer to a DXGK_VIDPNTOPOLOGY_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN topology object.

