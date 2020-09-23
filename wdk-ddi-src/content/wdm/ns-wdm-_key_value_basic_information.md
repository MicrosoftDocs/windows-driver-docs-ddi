---
UID: NS:wdm._KEY_VALUE_BASIC_INFORMATION
title: _KEY_VALUE_BASIC_INFORMATION (wdm.h)
description: The KEY_VALUE_BASIC_INFORMATION structure defines a subset of the full information available for a value entry of a registry key.
old-location: kernel\key_value_basic_information.htm
tech.root: kernel
ms.assetid: b3b14c21-3613-4f84-9e7d-368c4cc3fa9d
ms.date: 04/30/2018
keywords: ["KEY_VALUE_BASIC_INFORMATION structure"]
ms.keywords: "*PKEY_VALUE_BASIC_INFORMATION, KEY_VALUE_BASIC_INFORMATION, KEY_VALUE_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_VALUE_BASIC_INFORMATION, PKEY_VALUE_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VALUE_BASIC_INFORMATION, kernel.key_value_basic_information, kstruct_c_ba44285c-18a4-4a35-a31b-c2a6573d7023.xml, wdm/KEY_VALUE_BASIC_INFORMATION, wdm/PKEY_VALUE_BASIC_INFORMATION"
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
targetos: Windows
req.typenames: KEY_VALUE_BASIC_INFORMATION, *PKEY_VALUE_BASIC_INFORMATION
f1_keywords:
 - _KEY_VALUE_BASIC_INFORMATION
 - wdm/_KEY_VALUE_BASIC_INFORMATION
 - PKEY_VALUE_BASIC_INFORMATION
 - wdm/PKEY_VALUE_BASIC_INFORMATION
 - KEY_VALUE_BASIC_INFORMATION
 - wdm/KEY_VALUE_BASIC_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - KEY_VALUE_BASIC_INFORMATION
---

# _KEY_VALUE_BASIC_INFORMATION structure


## -description

The <b>KEY_VALUE_BASIC_INFORMATION</b> structure defines a subset of the full information available for a value entry of a registry key.

## -struct-fields

### -field TitleIndex

Device and intermediate drivers should ignore this member.

### -field Type

Specifies the system-defined type for the value entry in the registry key, which is one of the following:

<table>
<tr>
<th>REG_<i>XXX</i> type</th>
<th>Value</th>
</tr>
<tr>
<td>
REG_BINARY

</td>
<td>
Binary data in any form

</td>
</tr>
<tr>
<td>
REG_DWORD

</td>
<td>
A 4-byte numerical value

</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN

</td>
<td>
A 4-byte numerical value whose least significant byte is at the lowest address

</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN

</td>
<td>
A 4-byte numerical  value whose least significant byte is at the highest address

</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ

</td>
<td>
A null-terminated Unicode string, containing unexpanded references to environment variables, such as "%PATH%"

</td>
</tr>
<tr>
<td>
REG_LINK

</td>
<td>
A Unicode string naming a symbolic link. This type is irrelevant to device and intermediate drivers

</td>
</tr>
<tr>
<td>
REG_MULTI_SZ

</td>
<td>
An array of null-terminated strings, terminated by another zero

</td>
</tr>
<tr>
<td>
REG_NONE

</td>
<td>
Data with no particular type

</td>
</tr>
<tr>
<td>
REG_SZ

</td>
<td>
A null-terminated Unicode string

</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST

</td>
<td colspan="2">
A device driver's list of hardware resources, used by the driver or one of the physical devices it controls, in the <b>\ResourceMap</b> tree

</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST

</td>
<td colspan="2">
A device driver's list of possible hardware resources it or one of the physical devices it controls can use, from which the system writes a subset into the <b>\ResourceMap</b> tree

</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR

</td>
<td colspan="2">
A list of hardware resources that a physical device is using, detected and written into the <b>\HardwareDescription</b> tree by the system

</td>
</tr>
</table>

### -field NameLength

Specifies the size in bytes of the following value entry name.

### -field Name

A string of Unicode characters naming a value entry of the key.

## -remarks

A kernel-mode driver can obtain a <b>KEY_VALUE_BASIC_INFORMATION</b> that describes a registry key by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a>