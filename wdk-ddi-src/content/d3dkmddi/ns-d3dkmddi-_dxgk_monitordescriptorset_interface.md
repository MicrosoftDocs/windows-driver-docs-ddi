---
UID: NS:d3dkmddi._DXGK_MONITORDESCRIPTORSET_INTERFACE
title: _DXGK_MONITORDESCRIPTORSET_INTERFACE (d3dkmddi.h)
description: The DXGK_MONITORDESCRIPTORSET_INTERFACE structure contains pointers to functions that belong to the Monitor Descriptor Set Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitordescriptorset_interface.htm
ms.assetid: ac492a44-f14e-4b66-9ec1-4f1b04806646
ms.date: 05/10/2018
keywords: ["DXGK_MONITORDESCRIPTORSET_INTERFACE structure"]
ms.keywords: DXGK_MONITORDESCRIPTORSET_INTERFACE, DXGK_MONITORDESCRIPTORSET_INTERFACE structure [Display Devices], DmStructs_da0cca60-6df0-480b-8e02-0affe5eb5cfd.xml, _DXGK_MONITORDESCRIPTORSET_INTERFACE, d3dkmddi/DXGK_MONITORDESCRIPTORSET_INTERFACE, display.dxgk_monitordescriptorset_interface
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
req.typenames: DXGK_MONITORDESCRIPTORSET_INTERFACE
f1_keywords:
 - _DXGK_MONITORDESCRIPTORSET_INTERFACE
 - d3dkmddi/_DXGK_MONITORDESCRIPTORSET_INTERFACE
 - DXGK_MONITORDESCRIPTORSET_INTERFACE
 - d3dkmddi/DXGK_MONITORDESCRIPTORSET_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_MONITORDESCRIPTORSET_INTERFACE
---

# _DXGK_MONITORDESCRIPTORSET_INTERFACE structure


## -description

The DXGK_MONITORDESCRIPTORSET_INTERFACE structure contains pointers to functions that belong to the Monitor descriptor set interface, which is implemented by the [video present network (VidPN) manager](https://docs.microsoft.com/windows-hardware/drivers/display/vidpn-objects-and-interfaces).

## -struct-fields

### -field pfnGetNumDescriptors

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_getnumdescriptors">pfnGetNumDescriptors</a> function.

### -field pfnAcquireFirstDescriptorInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo">pfnAcquireFirstDescriptorInfo</a> function.

### -field pfnAcquireNextDescriptorInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo">pfnAcquireNextDescriptorInfo</a> function.

### -field pfnReleaseDescriptorInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo">pfnReleaseDescriptorInfo</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo">pfnAcquireFirstDescriptorInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo">pfnAcquireNextDescriptorInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_getnumdescriptors">pfnGetNumDescriptors</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo">pfnReleaseDescriptorInfo</a>

