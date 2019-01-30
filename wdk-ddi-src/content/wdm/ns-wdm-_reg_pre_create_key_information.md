---
UID: NS:wdm._REG_PRE_CREATE_KEY_INFORMATION
title: "_REG_PRE_CREATE_KEY_INFORMATION" (wdm.h)
description: The REG_PRE_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened.
old-location: kernel\reg_pre_open_key_information.htm
tech.root: kernel
ms.assetid: 9b7240b5-429b-4bf2-aa7b-373b63bb79ae
ms.date: 04/30/2018
ms.keywords: "*PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION, PREG_PRE_CREATE_KEY_INFORMATION, PREG_PRE_CREATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_CREATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], REG_PRE_OPEN_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_PRE_CREATE_KEY_INFORMATION, kernel.reg_pre_open_key_information, kstruct_d_dc0e8cf3-5084-4d54-8767-50b4ff043da8.xml, wdm/PREG_PRE_CREATE_KEY_INFORMATION, wdm/REG_PRE_CREATE_KEY_INFORMATION, wdm/REG_PRE_OPEN_KEY_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available only on Microsoft Windows XP.
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
-	Wdm.h
api_name:
-	REG_PRE_CREATE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION, *PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION
---

# _REG_PRE_CREATE_KEY_INFORMATION structure


## -description


The <b>REG_PRE_OPEN_KEY_INFORMATION</b> structure contains the name of a registry key that is about to be opened.


## -struct-fields




### -field CompleteName

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the complete path of the registry key.


## -remarks



For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
 

 

