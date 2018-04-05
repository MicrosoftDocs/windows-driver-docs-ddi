---
UID: NS:dispmprt._DXGK_OPM_INTERFACE
title: "_DXGK_OPM_INTERFACE"
author: windows-driver-content
description: The DXGK_OPM_INTERFACE structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface.htm
old-project: display
ms.assetid: 6ae1d9a8-db9a-460d-b258-222a2bd96265
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE structure [Display Devices], DmStructs_e1644da8-220d-470a-b9b9-f23ba7e1c4f6.xml, PDXGK_OPM_INTERFACE, PDXGK_OPM_INTERFACE structure pointer [Display Devices], _DXGK_OPM_INTERFACE, display.dxgk_opm_interface, dispmprt/DXGK_OPM_INTERFACE, dispmprt/PDXGK_OPM_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_OPM_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGK_OPM_INTERFACE, *PDXGK_OPM_INTERFACE
---

# _DXGK_OPM_INTERFACE structure


## -description


The DXGK_OPM_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/8dc171f7-76ca-4e1a-865e-7dcb6ab9a2e9">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.


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


## -remarks



A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's <a href="https://msdn.microsoft.com/d8255f36-be3a-4b19-ac8d-8748ac9b6a24">DxgkDdiQueryInterface</a> function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see <a href="https://msdn.microsoft.com/84218245-f5f3-4a6f-88ed-9cd5db224e30">Retrieving the OPM DDI</a>.




## -see-also




<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a>



<a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMDestroyProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3c055598-5f07-46e1-830d-1df9a459f742">DxgkDdiOPMGetCertificate</a>



<a href="https://msdn.microsoft.com/fe4197ad-52a2-47b3-ad96-57ea73cd931f">DxgkDdiOPMGetCertificateSize</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>



<a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a>



<a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



<a href="https://msdn.microsoft.com/d8255f36-be3a-4b19-ac8d-8748ac9b6a24">DxgkDdiQueryInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>
 

 

