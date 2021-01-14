---
UID: NS:wdm._REG_SET_VALUE_KEY_INFORMATION
title: _REG_SET_VALUE_KEY_INFORMATION (wdm.h)
description: The REG_SET_VALUE_INFORMATION structure describes a new setting for a registry key's value entry.
old-location: kernel\reg_set_value_key_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["REG_SET_VALUE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_SET_VALUE_KEY_INFORMATION, PREG_SET_VALUE_KEY_INFORMATION, PREG_SET_VALUE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_SET_VALUE_KEY_INFORMATION, REG_SET_VALUE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_SET_VALUE_KEY_INFORMATION, kernel.reg_set_value_key_information, kstruct_d_302658bd-6aaa-4878-9a67-a66c7307a4fa.xml, wdm/PREG_SET_VALUE_KEY_INFORMATION, wdm/REG_SET_VALUE_KEY_INFORMATION"
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
targetos: Windows
req.typenames: REG_SET_VALUE_KEY_INFORMATION, *PREG_SET_VALUE_KEY_INFORMATION
f1_keywords:
 - _REG_SET_VALUE_KEY_INFORMATION
 - wdm/_REG_SET_VALUE_KEY_INFORMATION
 - PREG_SET_VALUE_KEY_INFORMATION
 - wdm/PREG_SET_VALUE_KEY_INFORMATION
 - REG_SET_VALUE_KEY_INFORMATION
 - wdm/REG_SET_VALUE_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _REG_SET_VALUE_KEY_INFORMATION
 - PREG_SET_VALUE_KEY_INFORMATION
 - REG_SET_VALUE_KEY_INFORMATION
---

# _REG_SET_VALUE_KEY_INFORMATION structure


## -description

The <b>REG_SET_VALUE_INFORMATION</b> structure describes a new setting for a registry key's value entry.

## -struct-fields

### -field Object

A pointer to the registry key object for the key whose value entry is about to be changed.

### -field ValueName

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the value entry about to be changed.

### -field TitleIndex

Reserved for system use. Drivers should ignore this member.

### -field Type

The type of data that is about to be written. For more information about the possible values for this member, see the <i>Type</i> parameter of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>.

### -field Data

A pointer to a buffer that contains the data about to be written. The format of the buffer depends on the value of <b>Type</b>. For more information, see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>.

### -field DataSize

The size, in bytes, of the <b>Data</b> buffer.

### -field CallContext

Optional driver-defined context information that the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## -remarks

The system passes this structure to a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to set a value entry for a key—for example, when a user-mode thread calls <b>RegSetValue</b> or <b>RegSetValueEx</b> or when a driver calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>.

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>

