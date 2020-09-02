---
UID: NF:portcls.IRegistryKey.SetValueKey
title: IRegistryKey::SetValueKey (portcls.h)
description: The SetValueKey method replaces or creates a value entry under the open key.
old-location: audio\iregistrykey_setvaluekey.htm
tech.root: audio
ms.assetid: 4f9dd025-b49f-44ab-88c4-38139e6cbee2
ms.date: 05/08/2018
keywords: ["IRegistryKey::SetValueKey"]
ms.keywords: IRegistryKey interface [Audio Devices],SetValueKey method, IRegistryKey.SetValueKey, IRegistryKey::SetValueKey, SetValueKey, SetValueKey method [Audio Devices], SetValueKey method [Audio Devices],IRegistryKey interface, audio.iregistrykey_setvaluekey, audmp-routines_a7668b45-2b58-4a49-b1ef-a8d0755225b0.xml, portcls/IRegistryKey::SetValueKey
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IRegistryKey::SetValueKey
 - portcls/IRegistryKey::SetValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IRegistryKey.SetValueKey
---

# IRegistryKey::SetValueKey


## -description

The <code>SetValueKey</code> method replaces or creates a value entry under the open key.

## -parameters

### -param ValueName 

[in, optional]
Pointer to a string containing the name of the value entry to set. The name string is specified by a structure of type <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>. If the value entry has no name, set this parameter to <b>NULL</b>. If the caller specifies a name string but the given name is not unique relative to its containing key, the method replaces the data for an existing value entry.

### -param Type 

[in]
Specifies the type of the data to be written for <i>ValueName</i>. Set this parameter to one of the following system-defined types:

REG_BINARY

REG_DWORD

REG_DWORD_LITTLE_ENDIAN

REG_DWORD_BIG_ENDIAN

REG_EXPAND_SZ

REG_LINK

REG_MULTI_SZ

REG_NONE

REG_SZ

REG_RESOURCE_LIST

REG_RESOURCE_REQUIREMENTS_LIST

REG_FULL_RESOURCE_DESCRIPTOR

These parameter types are explained in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>.

### -param Data 

[in]
Pointer to a buffer containing the data. This parameter points to a user-supplied structure or value appropriate to the function.

### -param DataSize 

[in]
Specifies the size in bytes of <i>Data</i>. This parameter specifies how many bytes of data the method will copy from the buffer that <i>Data</i> points to.

## -returns

<code>SetValueKey</code> returns STATUS_SUCCESS if the call was successful in setting the specified value key. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameters passed to the method is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that method was unable to find the named value key.

</td>
</tr>
</table>

## -remarks

If the given key has no existing value entry with a name matching the given <i>ValueName</i>, <code>SetValueKey</code> creates a new value entry with the given name. If a matching value entry name exists, this routine overwrites the original value entry for the given <i>ValueName</i>. Thus, <code>SetValueKey</code> preserves a unique name for each value entry of any particular key. While each value entry name must be unique to its containing key, many different keys in the registry can have value entries with the same names.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iregistrykey">IRegistryKey</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>

