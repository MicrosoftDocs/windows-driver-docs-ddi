---
UID: NS:wdfdriver._WDF_DRIVER_VERSION_AVAILABLE_PARAMS
title: "_WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
author: windows-driver-content
description: The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure specifies major and minor version numbers for the Kernel-Mode Driver Framework's library.
old-location: wdf\wdf_driver_version_available_params.htm
tech.root: wdf
ms.assetid: 7f5192ac-aea0-4e63-b2f9-1d51e00bbf03
ms.date: 2/26/2018
ms.keywords: "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, DFDriverObjectRef_dea9dee4-b36b-4672-89cb-bbffe0a78f3b.xml, PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, PWDF_DRIVER_VERSION_AVAILABLE_PARAMS structure pointer, WDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure, _WDF_DRIVER_VERSION_AVAILABLE_PARAMS, kmdf.wdf_driver_version_available_params, wdf.wdf_driver_version_available_params, wdfdriver/PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, wdfdriver/WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
ms.topic: struct
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfdriver.h
api_name:
-	WDF_DRIVER_VERSION_AVAILABLE_PARAMS
product:
- Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
---

# _WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure specifies major and minor version numbers for the Kernel-Mode Driver Framework's library.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field MajorVersion

A numeric value that represents the Kernel-Mode Driver Framework library's major version number.


### -field MinorVersion

A numeric value that represents the Kernel-Mode Driver Framework library's minor version number.


## -remarks



The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547190">WdfDriverIsVersionAvailable</a> method. Drivers should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551309">WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT</a> to initialize this structure before calling <b>WdfDriverIsVersionAvailable</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551309">WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547190">WdfDriverIsVersionAvailable</a>
 

 

