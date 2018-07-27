---
UID: NS:aux_klib._AUX_MODULE_BASIC_INFO
title: "_AUX_MODULE_BASIC_INFO"
author: windows-driver-content
description: The AUX_MODULE_BASIC_INFO structure contains basic information about a loaded image module.
old-location: kernel\aux_module_basic_info.htm
tech.root: kernel
ms.assetid: 8cee85a3-b2e4-4378-a700-862d1b517f14
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PAUX_MODULE_BASIC_INFO, AUX_MODULE_BASIC_INFO, AUX_MODULE_BASIC_INFO structure [Kernel-Mode Driver Architecture], PAUX_MODULE_BASIC_INFO, PAUX_MODULE_BASIC_INFO structure pointer [Kernel-Mode Driver Architecture], _AUX_MODULE_BASIC_INFO, aux_klib/AUX_MODULE_BASIC_INFO, aux_klib/PAUX_MODULE_BASIC_INFO, aux_klib_7c33c85c-d2d1-49ea-98e2-d25299a281b9.xml, kernel.aux_module_basic_info"
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
-	AUX_MODULE_BASIC_INFO
product:
- Windows
targetos: Windows
req.typenames: AUX_MODULE_BASIC_INFO, *PAUX_MODULE_BASIC_INFO
---

# _AUX_MODULE_BASIC_INFO structure


## -description


The <b>AUX_MODULE_BASIC_INFO</b> structure contains basic information about a loaded image module.


## -struct-fields




### -field ImageBase

A pointer to the base of the loaded image. 


## -remarks



The <b>AUX_MODULE_BASIC_INFO</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a>
 

 

