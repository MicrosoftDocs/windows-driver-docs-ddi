---
UID: NF:wdfdriver.WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
title: WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function
author: windows-driver-content
description: The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes a WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure.
old-location: wdf\wdf_driver_version_available_params_init.htm
old-project: wdf
ms.assetid: aba3844e-745d-4d2c-9855-0535f53d7b0a
ms.author: windowsdriverdev
ms.date: 2/20/2018
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
req.lib: NtosKrnl.exe
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
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes a <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure.


## -syntax


````
VOID WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(
  _Out_ PWDF_DRIVER_VERSION_AVAILABLE_PARAMS Params,
  _In_  ULONG                                MajorVersion,
  _In_  ULONG                                MinorVersion
);
````


## -parameters




### -param Params [out]

A pointer to a <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure.


### -param MajorVersion [in]

A numeric value that represents the Kernel-Mode Driver Framework library's major version number.


### -param MinorVersion [in]

A numeric value that represents the Kernel-Mode Driver Framework library's minor version number.


## -returns



None




## -remarks



The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function zeros the <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a> structure that the <i>Params</i> parameter points to and sets the structure's <b>Size</b> member. Then, this function sets the structure's <b>MajorVersion</b> and <b>MinorVersion</b> members to the specified values.


#### Examples

For a code example that uses WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT, see <a href="..\wdfdriver\nf-wdfdriver-wdfdriverisversionavailable.md">WdfDriverIsVersionAvailable</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_version_available_params.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

