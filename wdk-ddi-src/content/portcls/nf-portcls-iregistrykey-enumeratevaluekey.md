---
UID: NF:portcls.IRegistryKey.EnumerateValueKey
title: IRegistryKey::EnumerateValueKey (portcls.h)
description: The EnumerateValueKey method returns information about a registry entry that contains a value key.
old-location: audio\iregistrykey_enumeratevaluekey.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IRegistryKey::EnumerateValueKey"]
ms.keywords: EnumerateValueKey, EnumerateValueKey method [Audio Devices], EnumerateValueKey method [Audio Devices],IRegistryKey interface, IRegistryKey interface [Audio Devices],EnumerateValueKey method, IRegistryKey.EnumerateValueKey, IRegistryKey::EnumerateValueKey, audio.iregistrykey_enumeratevaluekey, audmp-routines_8b4fc752-24a3-4331-b90b-85642dc2121a.xml, portcls/IRegistryKey::EnumerateValueKey
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
 - IRegistryKey::EnumerateValueKey
 - portcls/IRegistryKey::EnumerateValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IRegistryKey::EnumerateValueKey
---

# IRegistryKey::EnumerateValueKey


## -description

The <code>EnumerateValueKey</code> method returns information about a registry entry that contains a value key.

## -parameters

### -param Index 

[in]
Specifies the subkey index. This parameter identifies the subkey whose value is requested. If the key contains <i>n</i> subkeys, valid indices range from 0 to <i>n</i>-1. If the index exceeds this range, the method returns STATUS_NO_MORE_ENTRIES.

### -param KeyValueInformationClass 

[in]
Specifies the type of information to be returned in the buffer. Set this parameter to one of the following KEY_VALUE_INFORMATION_CLASS enumeration values:

<ul>
<li>
<b>KeyValueBasicInformation</b>

</li>
<li>
<code>KeyValueFullInformation</code>

</li>
<li>
<code>KeyValuePartialInformation</code>

</li>
</ul>

### -param KeyValueInformation 

[out]
Output pointer for the key value. This parameter points to a caller-allocated buffer into which the method writes the requested data. The buffer contains a structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>, or <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>, depending on the value of <i>KeyValueInformationClass</i>. The structure is followed by additional data whose size depends on the data type of the key value.

### -param Length 

[in]
Size in bytes of the <i>KeyValueInformation</i> buffer, which the caller must set according to the given <i>KeyValueInformationClass</i>. For the call to succeed, the buffer must be at least as large as the data that the method writes into the buffer.

### -param ResultLength 

[out]
Output pointer for the length of the resulting data. This parameter points to a caller-allocated ULONG variable into which the method writes a count specifying the number of bytes actually written into the <i>KeyValueInformation</i> buffer. If the specified buffer length is too small to contain the information, however, the method instead outputs the required buffer size and returns STATUS_BUFFER_OVERFLOW.

## -returns

<code>EnumerateValueKey</code> returns STATUS_SUCCESS if the call was successful in copying the requested information into the <i>KeyValueInformation</i> buffer. If the specified buffer size is too small to receive all of the available information, the method returns STATUS_BUFFER_OVERFLOW. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specified buffer is too small to receive any information.

</td>
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
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no more value keys are available (the <i>Index</i> parameter is greater than or equal to the number of value keys).

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iregistrykey">IRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>

