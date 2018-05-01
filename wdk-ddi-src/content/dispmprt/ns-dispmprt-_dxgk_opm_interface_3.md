---
UID: NS:dispmprt._DXGK_OPM_INTERFACE_3
title: "_DXGK_OPM_INTERFACE_3"
author: windows-driver-content
description: The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface_3.htm
old-project: display
ms.assetid: 0BD6BA91-7F46-482B-B808-DEB8A23A0B84
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PDXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3 structure [Display Devices], PDXGK_OPM_INTERFACE_3, PDXGK_OPM_INTERFACE_3 structure pointer [Display Devices], _DXGK_OPM_INTERFACE_3, display.dxgk_opm_interface_3, dispmprt/DXGK_OPM_INTERFACE_3, dispmprt/PDXGK_OPM_INTERFACE_3"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dispmprt.h
api_name:
-	DXGK_OPM_INTERFACE_3
product: Windows
targetos: Windows
req.typenames: DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3
---

# _DXGK_OPM_INTERFACE_3 structure


## -description


The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the <a href="https://msdn.microsoft.com/8dc171f7-76ca-4e1a-865e-7dcb6ab9a2e9">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The <b>Version</b> member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in Dispmprt.h.


### -field Context

A pointer to a private context block. <b>Context</b> must be set to <b>NULL</b>.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure.


### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/fe4197ad-52a2-47b3-ad96-57ea73cd931f">DxgkDdiOPMGetCertificateSize</a> function.


### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/3c055598-5f07-46e1-830d-1df9a459f742">DxgkDdiOPMGetCertificate</a> function.


### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a> function.


### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a> function.


### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function.


### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> function.


### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a> function.


### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMDestroyProtectedOutput</a> function.


### -field DxgkDdiOPMCreateProtectedOutputNonLocalDisplay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMCreateProtectedOutputNonLocalDisplay</a> function.


### -field DxgkDdiOPMSetSrmList

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMSetSrmList</a> function.


### -field DxgkDdiOPMGetSrmListVersion

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMGetSrmListVersion</a> function.

