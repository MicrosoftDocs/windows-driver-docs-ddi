---
UID: NS:aux_klib._AUX_MODULE_EXTENDED_INFO
title: "_AUX_MODULE_EXTENDED_INFO"
author: windows-driver-content
description: The AUX_MODULE_EXTENDED_INFO structure contains extended information about a loaded image module.
old-location: kernel\aux_module_extended_info.htm
old-project: kernel
ms.assetid: 9733b17d-c990-4eda-87e2-906f2f78c5d5
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	aux_klib.h
apiname:
-	AUX_MODULE_EXTENDED_INFO
product: Windows
targetos: Windows
req.typenames: AUX_MODULE_EXTENDED_INFO, *PAUX_MODULE_EXTENDED_INFO
---

# _AUX_MODULE_EXTENDED_INFO structure


## -description


The <b>AUX_MODULE_EXTENDED_INFO</b> structure contains extended information about a loaded image module.


## -syntax


````
typedef struct _AUX_MODULE_EXTENDED_INFO {
  AUX_MODULE_BASIC_INFO BasicInfo;
  ULONG                 ImageSize;
  USHORT                FileNameOffset;
  UCHAR                 FullPathName[AUX_KLIB_MODULE_PATH_LEN];
} AUX_MODULE_EXTENDED_INFO, *PAUX_MODULE_EXTENDED_INFO;
````


## -struct-fields




### -field BasicInfo

An <a href="..\aux_klib\ns-aux_klib-_aux_module_basic_info.md">AUX_MODULE_BASIC_INFO</a> structure.


### -field ImageSize

The size, in bytes, of the loaded image.


### -field FileNameOffset

The offset, in bytes, from the beginning of the full path name to the file name of the module's image file.


### -field FullPathName

The full path name of the module's image file.


## -remarks



The <b>AUX_MODULE_EXTENDED_INFO</b> structure is used as input to the <a href="..\aux_klib\nf-aux_klib-auxklibquerymoduleinformation.md">AuxKlibQueryModuleInformation</a> routine. 




## -see-also

<a href="..\aux_klib\nf-aux_klib-auxklibquerymoduleinformation.md">AuxKlibQueryModuleInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AUX_MODULE_EXTENDED_INFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

