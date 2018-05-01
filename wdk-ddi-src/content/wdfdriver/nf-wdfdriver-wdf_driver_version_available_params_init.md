---
UID: NF:wdfdriver.WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
title: WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function
author: windows-driver-content
description: The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes a WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure.
old-location: wdf\wdf_driver_version_available_params_init.htm
old-project: wdf
ms.assetid: aba3844e-745d-4d2c-9855-0535f53d7b0a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_9638f416-7d77-45af-8e87-07c51198fb05.xml, WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT, WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function, kmdf.wdf_driver_version_available_params_init, wdf.wdf_driver_version_available_params_init, wdfdriver/WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
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
-	WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure.


## -parameters




### -param Params [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure.


### -param MajorVersion [in]

A numeric value that represents the Kernel-Mode Driver Framework library's major version number.


### -param MinorVersion [in]

A numeric value that represents the Kernel-Mode Driver Framework library's minor version number.


## -returns



None




## -remarks



The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure that the <i>Params</i> parameter points to and sets the structure's <b>Size</b> member. Then, this function sets the structure's <b>MajorVersion</b> and <b>MinorVersion</b> members to the specified values.


#### Examples

For a code example that uses WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547190">WdfDriverIsVersionAvailable</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551306">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a>
 

 

