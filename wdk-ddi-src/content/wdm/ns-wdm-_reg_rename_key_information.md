---
UID: NS:wdm._REG_RENAME_KEY_INFORMATION
title: _REG_RENAME_KEY_INFORMATION (wdm.h)
description: The REG_RENAME_KEY_INFORMATION structure contains the new name for a registry key whose name is about to be changed.
old-location: kernel\reg_rename_key_information.htm
tech.root: kernel
ms.assetid: 80ffa1dc-aa4f-40b4-936b-7e441b3b123d
ms.date: 04/30/2018
keywords: ["_REG_RENAME_KEY_INFORMATION structure"]
ms.keywords: "*PREG_RENAME_KEY_INFORMATION, PREG_RENAME_KEY_INFORMATION, PREG_RENAME_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_RENAME_KEY_INFORMATION, REG_RENAME_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_RENAME_KEY_INFORMATION, kernel.reg_rename_key_information, kstruct_d_f6416cfd-5ace-4366-81a5-87b233551c7a.xml, wdm/PREG_RENAME_KEY_INFORMATION, wdm/REG_RENAME_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_RENAME_KEY_INFORMATION"
 - "REG_RENAME_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- REG_RENAME_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_RENAME_KEY_INFORMATION, *PREG_RENAME_KEY_INFORMATION
---

# _REG_RENAME_KEY_INFORMATION structure


## -description


The <b>REG_RENAME_KEY_INFORMATION</b> structure contains the new name for a registry key whose name is about to be changed. 


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose name is about to be changed.


### -field NewName

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the new name for the registry key.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



Note that when a key is renamed, only the last component of the path can be changed.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

