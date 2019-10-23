---
UID: NF:aux_klib.AuxKlibGetImageExportDirectory
title: AuxKlibGetImageExportDirectory function (aux_klib.h)
description: The AuxKlibGetImageExportDirectory routine returns an image module's export directory.
old-location: kernel\auxklibgetimageexportdirectory.htm
tech.root: kernel
ms.assetid: 994ba853-88b6-4456-8fdb-3199979df05e
ms.date: 04/30/2018
ms.keywords: AuxKlibGetImageExportDirectory, AuxKlibGetImageExportDirectory routine [Kernel-Mode Driver Architecture], aux_klib/AuxKlibGetImageExportDirectory, aux_klib_266e4e59-eaf6-47a4-a5d0-27fc55426273.xml, kernel.auxklibgetimageexportdirectory
ms.topic: function
f1_keywords:
 - "aux_klib/AuxKlibGetImageExportDirectory"
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Aux_Klib.lib
- Aux_Klib.dll
api_name:
- AuxKlibGetImageExportDirectory
product:
- Windows
targetos: Windows
req.typenames: 
---

# AuxKlibGetImageExportDirectory function


## -description


The <b>AuxKlibGetImageExportDirectory</b> routine returns an image module's export directory.


## -parameters




### -param ImageBase [in]

A pointer to the base of an image, which is obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibquerymoduleinformation">AuxKlibQueryModuleInformation</a>. 


## -returns



<b>AuxKlibGetImageExportDirectory</b> returns a pointer to an <b>IMAGE_EXPORT_DIRECTORY</b> structure. This structure is defined in Ntimage.h, which is included in the Microsoft Windows Driver Kit (WDK).




## -remarks



Drivers must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibinitialize">AuxKlibInitialize</a> before calling <b>AuxKlibGetImageExportDirectory</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibquerymoduleinformation">AuxKlibQueryModuleInformation</a>
 

 

