---
UID: NS:aux_klib._AUX_MODULE_EXTENDED_INFO
title: "_AUX_MODULE_EXTENDED_INFO"
author: windows-driver-content
description: The AUX_MODULE_EXTENDED_INFO structure contains extended information about a loaded image module.
old-location: kernel\aux_module_extended_info.htm
old-project: kernel
ms.assetid: 9733b17d-c990-4eda-87e2-906f2f78c5d5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PAUX_MODULE_EXTENDED_INFO, AUX_MODULE_EXTENDED_INFO, AUX_MODULE_EXTENDED_INFO structure [Kernel-Mode Driver Architecture], PAUX_MODULE_EXTENDED_INFO, PAUX_MODULE_EXTENDED_INFO structure pointer [Kernel-Mode Driver Architecture], _AUX_MODULE_EXTENDED_INFO, aux_klib/AUX_MODULE_EXTENDED_INFO, aux_klib/PAUX_MODULE_EXTENDED_INFO, aux_klib_670e2af9-0080-49b9-85c4-06a6b1ae06c6.xml, kernel.aux_module_extended_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: aux_klib.h
req.include-header: Aux_klib.h
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
-	aux_klib.h
api_name:
-	AUX_MODULE_EXTENDED_INFO
product:
- Windows
targetos: Windows
req.typenames: AUX_MODULE_EXTENDED_INFO, *PAUX_MODULE_EXTENDED_INFO
---

# _AUX_MODULE_EXTENDED_INFO structure


## -description


The <b>AUX_MODULE_EXTENDED_INFO</b> structure contains extended information about a loaded image module.


## -struct-fields




### -field BasicInfo

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540641">AUX_MODULE_BASIC_INFO</a> structure.


### -field ImageSize

The size, in bytes, of the loaded image.


### -field FileNameOffset

The offset, in bytes, from the beginning of the full path name to the file name of the module's image file.


### -field FullPathName

The full path name of the module's image file.


## -remarks



The <b>AUX_MODULE_EXTENDED_INFO</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a> routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a>
 

 

