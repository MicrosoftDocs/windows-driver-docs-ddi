---
UID: NS:wdm._REG_SET_INFORMATION_KEY_INFORMATION
title: _REG_SET_INFORMATION_KEY_INFORMATION (wdm.h)
description: The REG_SET_INFORMATION_KEY_INFORMATION structure describes a new setting for a key's metadata.
old-location: kernel\reg_set_information_key_information.htm
tech.root: kernel
ms.assetid: 30b29bda-9cd9-4fc8-b168-e66f69b82358
ms.date: 04/30/2018
keywords: ["_REG_SET_INFORMATION_KEY_INFORMATION structure"]
ms.keywords: "*PREG_SET_INFORMATION_KEY_INFORMATION, PREG_SET_INFORMATION_KEY_INFORMATION, PREG_SET_INFORMATION_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_SET_INFORMATION_KEY_INFORMATION, REG_SET_INFORMATION_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_SET_INFORMATION_KEY_INFORMATION, kernel.reg_set_information_key_information, kstruct_d_f6265b80-6f92-4856-bb8e-49cc97a1c553.xml, wdm/PREG_SET_INFORMATION_KEY_INFORMATION, wdm/REG_SET_INFORMATION_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_SET_INFORMATION_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- REG_SET_INFORMATION_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_SET_INFORMATION_KEY_INFORMATION, *PREG_SET_INFORMATION_KEY_INFORMATION
---

# _REG_SET_INFORMATION_KEY_INFORMATION structure


## -description


The <b>REG_SET_INFORMATION_KEY_INFORMATION</b> structure describes a new setting for a key's metadata.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose metadata is about to be changed.


### -field KeySetInformationClass

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_set_information_class">KEY_SET_INFORMATION_CLASS</a> value that indicates the type of information about to be changed.


### -field KeySetInformation

A pointer to a buffer that contains the information about to be written. The format of the buffer depends on the value of <b>KeySetInformationClass</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_set_information_class">KEY_SET_INFORMATION_CLASS</a>.


### -field KeySetInformationLength

The size, in bytes, of the <b>KeySetInformation</b> buffer.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

