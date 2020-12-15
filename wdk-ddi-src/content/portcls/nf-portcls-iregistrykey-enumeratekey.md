---
UID: NF:portcls.IRegistryKey.EnumerateKey
title: IRegistryKey::EnumerateKey (portcls.h)
description: The EnumerateKey method returns information about the subkeys of the open key.
old-location: audio\iregistrykey_enumeratekey.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IRegistryKey::EnumerateKey"]
ms.keywords: EnumerateKey, EnumerateKey method [Audio Devices], EnumerateKey method [Audio Devices],IRegistryKey interface, IRegistryKey interface [Audio Devices],EnumerateKey method, IRegistryKey.EnumerateKey, IRegistryKey::EnumerateKey, audio.iregistrykey_enumeratekey, audmp-routines_ef31b848-c963-4327-ba86-bca98383ad90.xml, portcls/IRegistryKey::EnumerateKey
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
 - IRegistryKey::EnumerateKey
 - portcls/IRegistryKey::EnumerateKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IRegistryKey.EnumerateKey
---

# IRegistryKey::EnumerateKey


## -description

The <code>EnumerateKey</code> method returns information about the subkeys of the open key.

## -parameters

### -param Index 

[in]
Specifies the subkey index. This parameter identifies the subkey for which key information is requested. If the key contains <i>n</i> subkeys, valid indices range from 0 to <i>n</i>-1. If the index exceeds this range, the method returns STATUS_NO_MORE_ENTRIES.

### -param KeyInformationClass 

[in]
Specifies the type of information to be returned in the buffer. Set this parameter to one of the following KEY_INFORMATION_CLASS enumeration values:

<ul>
<li>
<b>KeyBasicInformation</b>

</li>
<li>
<b>KeyFullInformation</b>

</li>
<li>
<b>KeyNodeInformation</b>

</li>
</ul>

### -param KeyInformation 

[out]
Pointer to the key information buffer. This parameter points to a caller-allocated buffer into which the method writes the requested data. The buffer contains a structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_basic_information">KEY_BASIC_INFORMATION</a>, <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_full_information">KEY_FULL_INFORMATION</a>, or <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_node_information">KEY_NODE_INFORMATION</a>, depending on the value of <i>KeyInformationClass</i>. The structure is followed by a string of Unicode characters whose size depends on the type of information being requested about the key.

### -param Length 

[in]
Specifies the size in bytes of the <i>KeyInformation</i> buffer, which the caller must set according to the given <i>KeyInformationClass</i>. For the call to succeed, the buffer must be at least as large as the data that the method writes into the buffer.

### -param ResultLength 

[out]
Output pointer for the length of the resulting data. This parameter points to a caller-allocated ULONG variable into which the method writes a count specifying the number of bytes actually written into the <i>KeyInformation</i> buffer. If the specified buffer length is too small to contain the information, however, the method instead outputs the required buffer size and returns STATUS_BUFFER_OVERFLOW.

## -returns

<code>EnumerateKey</code> returns STATUS_SUCCESS if the call was successful in retrieving the requested information in the <i>KeyInformation</i> buffer. If the specified buffer size is too small to receive all of the available information, the method returns STATUS_BUFFER_OVERFLOW. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

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
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no more subkeys are available (subkey index is larger than or equal to the number of subkeys).

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iregistrykey">IRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_basic_information">KEY_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_full_information">KEY_FULL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_node_information">KEY_NODE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey">ZwEnumerateKey</a>
