---
UID: NF:aux_klib.AuxKlibGetImageExportDirectory
title: AuxKlibGetImageExportDirectory function
author: windows-driver-content
description: The AuxKlibGetImageExportDirectory routine returns an image module's export directory.
old-location: kernel\auxklibgetimageexportdirectory.htm
old-project: kernel
ms.assetid: 994ba853-88b6-4456-8fdb-3199979df05e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: AuxKlibGetImageExportDirectory routine [Kernel-Mode Driver Architecture], aux_klib_266e4e59-eaf6-47a4-a5d0-27fc55426273.xml, AuxKlibGetImageExportDirectory, kernel.auxklibgetimageexportdirectory, aux_klib/AuxKlibGetImageExportDirectory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Aux_Klib.lib
-	Aux_Klib.dll
apiname:
-	AuxKlibGetImageExportDirectory
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---

# AuxKlibGetImageExportDirectory function


## -description


The <b>AuxKlibGetImageExportDirectory</b> routine returns an image module's export directory.


## -syntax


````
PIMAGE_EXPORT_DIRECTORY AuxKlibGetImageExportDirectory(
  _In_ PVOID ImageBase
);
````


## -parameters




### -param ImageBase [in]

A pointer to the base of an image, which is obtained by calling <a href="..\aux_klib\nf-aux_klib-auxklibquerymoduleinformation.md">AuxKlibQueryModuleInformation</a>. 


## -returns



<b>AuxKlibGetImageExportDirectory</b> returns a pointer to an <b>IMAGE_EXPORT_DIRECTORY</b> structure. This structure is defined in Ntimage.h, which is included in the Microsoft Windows Driver Kit (WDK).




## -remarks



Drivers must call <a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a> before calling <b>AuxKlibGetImageExportDirectory</b>.




## -see-also

<a href="..\aux_klib\nf-aux_klib-auxklibquerymoduleinformation.md">AuxKlibQueryModuleInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AuxKlibGetImageExportDirectory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

