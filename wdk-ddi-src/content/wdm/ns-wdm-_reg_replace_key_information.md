---
UID: NS:wdm._REG_REPLACE_KEY_INFORMATION
title: _REG_REPLACE_KEY_INFORMATION (wdm.h)
description: The REG_REPLACE_KEY_INFORMATION structure describes the metadata that is about to be replaced for a key.
old-location: kernel\reg_replace_key_information.htm
tech.root: kernel
ms.assetid: bbe60db6-85ae-480c-8852-80935a52697e
ms.date: 04/30/2018
keywords: ["_REG_REPLACE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_REPLACE_KEY_INFORMATION, PREG_REPLACE_KEY_INFORMATION, PREG_REPLACE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_REPLACE_KEY_INFORMATION, REG_REPLACE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_REPLACE_KEY_INFORMATION, kernel.reg_replace_key_information, kstruct_d_29e33c32-67fc-48e0-a976-9830278009bc.xml, wdm/PREG_REPLACE_KEY_INFORMATION, wdm/REG_REPLACE_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_REPLACE_KEY_INFORMATION"
 - "REG_REPLACE_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista SP2 and later versions of the Windows operating system.
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
- Wdm.h
api_name:
- REG_REPLACE_KEY_INFORMATION
targetos: Windows
req.typenames: REG_REPLACE_KEY_INFORMATION, *PREG_REPLACE_KEY_INFORMATION
---

# _REG_REPLACE_KEY_INFORMATION structure


## -description


The <b>REG_REPLACE_KEY_INFORMATION</b> structure describes the metadata that is about to be replaced for a key.


## -struct-fields




### -field Object

A pointer to a registry key object for the key whose metadata is about to be replaced.


### -field OldFileName

The name of the file that receives a backup copy of the registry information being replaced.


### -field NewFileName

The name of the file with the registry information. This file is typically created by using the <b>RegSaveKey</b> function.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes this structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to replace the metadata for a key.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

