---
UID: NS:d3dkmddi._DXGK_VIDPN_INTERFACE
title: _DXGK_VIDPN_INTERFACE (d3dkmddi.h)
description: The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the VidPn interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpn_interface.htm
ms.assetid: 7ddd110c-2521-4df6-a936-e702a0f15312
ms.date: 05/10/2018
ms.keywords: DXGK_VIDPN_INTERFACE, DXGK_VIDPN_INTERFACE structure [Display Devices], DmStructs_0fb940db-3ede-4eac-938b-89e34a9b337d.xml, _DXGK_VIDPN_INTERFACE, d3dkmddi/DXGK_VIDPN_INTERFACE, display.dxgk_vidpn_interface
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_VIDPN_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPN_INTERFACE
---

# _DXGK_VIDPN_INTERFACE structure


## -description


The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPn interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field Version

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_vidpn_interface_version">DXGK_VIDPN_INTERFACE_VERSION</a> enumerator that specifies the version of the interface.


### -field pfnGetTopology

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function.


### -field pfnAcquireSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function.


### -field pfnReleaseSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset">pfnReleaseSourceModeSet</a> function.


### -field pfnCreateNewSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset">pfnCreateNewSourceModeSet</a> function.


### -field pfnAssignSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset">pfnAssignSourceModeSet</a> function.


### -field pfnAssignMultisamplingMethodSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assignmultisamplingmethodset">pfnAssignMultisamplingMethodSet</a> function.


### -field pfnAcquireTargetModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function.


### -field pfnReleaseTargetModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a> function.


### -field pfnCreateNewTargetModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a> function.


### -field pfnAssignTargetModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a> function.


## -remarks



The display miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_queryvidpninterface">DxgkCbQueryVidPnInterface</a> to obtain a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.

For more information about the VidPN interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/vidpn-objects-and-interfaces">VidPN Objects and Interfaces</a>.



