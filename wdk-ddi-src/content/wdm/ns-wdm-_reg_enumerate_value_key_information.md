---
UID: NS:wdm._REG_ENUMERATE_VALUE_KEY_INFORMATION
title: _REG_ENUMERATE_VALUE_KEY_INFORMATION (wdm.h)
description: The REG_ENUMERATE_VALUE_KEY_INFORMATION structure describes one value entry of a key whose value entries are being enumerated.
old-location: kernel\reg_enumerate_value_key_information.htm
tech.root: kernel
ms.assetid: 0d5566ca-b71c-429e-bb7d-db3eb09f0472
ms.date: 04/30/2018
ms.keywords: "*PREG_ENUMERATE_VALUE_KEY_INFORMATION, PREG_ENUMERATE_VALUE_KEY_INFORMATION, PREG_ENUMERATE_VALUE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_ENUMERATE_VALUE_KEY_INFORMATION, REG_ENUMERATE_VALUE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_ENUMERATE_VALUE_KEY_INFORMATION, kernel.reg_enumerate_value_key_information, kstruct_d_126313cd-66b7-4239-8c2a-23c475d575cf.xml, wdm/PREG_ENUMERATE_VALUE_KEY_INFORMATION, wdm/REG_ENUMERATE_VALUE_KEY_INFORMATION"
ms.topic: struct
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
- Wdm.h
api_name:
- REG_ENUMERATE_VALUE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_ENUMERATE_VALUE_KEY_INFORMATION, *PREG_ENUMERATE_VALUE_KEY_INFORMATION
---

# _REG_ENUMERATE_VALUE_KEY_INFORMATION structure


## -description


The <b>REG_ENUMERATE_VALUE_KEY_INFORMATION</b> structure describes one value entry of a key whose value entries are being enumerated.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose value entries are being enumerated.


### -field Index

The zero-based index of the subkey within the key.


### -field KeyValueInformationClass

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a> value that indicates the type of information to be returned by the system in the <b>KeyValueInformation</b> buffer.


### -field KeyValueInformation

A pointer to a buffer that contains the information to be returned by the system. The format of the buffer depends on the value of <b>KeyValueInformationClass</b>. For more information see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a>.


### -field Length

The size, in bytes, of the <b>KeyValueInformation</b> buffer.


### -field ResultLength

A pointer to a variable that receives (from the system) the amount of valid data, in bytes, in the <b>KeyValueInformation</b> buffer.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes this structure to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to enumerate a value entry of a key—for example, when a user-mode thread calls <b>RegEnumValue</b> or when a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>
 

 

