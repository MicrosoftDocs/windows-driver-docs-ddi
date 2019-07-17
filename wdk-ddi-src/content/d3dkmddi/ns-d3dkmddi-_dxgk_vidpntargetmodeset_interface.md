---
UID: NS:d3dkmddi._DXGK_VIDPNTARGETMODESET_INTERFACE
title: _DXGK_VIDPNTARGETMODESET_INTERFACE (d3dkmddi.h)
description: The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Target Mode Set interface, which is implemented by the VidPN manager.
old-location: display\dxgk_vidpntargetmodeset_interface.htm
ms.assetid: 556d3134-942b-475c-adac-3087a512f481
ms.date: 05/10/2018
ms.keywords: DXGK_VIDPNTARGETMODESET_INTERFACE, DXGK_VIDPNTARGETMODESET_INTERFACE structure [Display Devices], DmStructs_f73ff16c-04e3-491b-9f0a-de50563abea4.xml, _DXGK_VIDPNTARGETMODESET_INTERFACE, d3dkmddi/DXGK_VIDPNTARGETMODESET_INTERFACE, display.dxgk_vidpntargetmodeset_interface
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_VIDPNTARGETMODESET_INTERFACE"
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
- DXGK_VIDPNTARGETMODESET_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPNTARGETMODESET_INTERFACE
---

# _DXGK_VIDPNTARGETMODESET_INTERFACE structure


## -description


The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPn Target Mode Set interface</a>, which is implemented by the VidPN manager.


## -struct-fields




### -field pfnGetNumModes

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_getnummodes">pfnGetNumModes</a> function.


### -field pfnAcquireFirstModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> function.


### -field pfnAcquireNextModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a> function.


### -field pfnAcquirePinnedModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirepinnedmodeinfo">pfnAcquirePinnedModeInfo</a> function.


### -field pfnReleaseModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a> function.


### -field pfnCreateNewModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> function.


### -field pfnAddMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode">pfnAddMode</a> function.


### -field pfnPinMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_pinmode">pfnPinMode</a> function.


## -remarks



The display miniport driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPn interface</a> to obtain a handle to a VidPN target mode set object and a pointer to a DXGK_VIDPNTARGETMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN target mode set object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a>
 

 

