---
UID: NF:portcls.IRegistryKey.QueryValueKey
title: IRegistryKey::QueryValueKey
author: windows-driver-content
description: The QueryValueKey method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.
old-location: audio\iregistrykey_queryvaluekey.htm
tech.root: audio
ms.assetid: 6339a8bf-ab32-48bc-aae6-2cce2a6a648d
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IRegistryKey interface [Audio Devices],QueryValueKey method, IRegistryKey.QueryValueKey, IRegistryKey::QueryValueKey, QueryValueKey, QueryValueKey method [Audio Devices], QueryValueKey method [Audio Devices],IRegistryKey interface, audio.iregistrykey_queryvaluekey, audmp-routines_2b41aa08-8b71-45af-bcfa-c33723c82c13.xml, portcls/IRegistryKey::QueryValueKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IRegistryKey.QueryValueKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRegistryKey::QueryValueKey


## -description


The <code>QueryValueKey</code> method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.


## -parameters




### -param ValueName [in]

Pointer to the manufacturer-supplied name of the value entry. The name string is specified by a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>.


### -param KeyValueInformationClass [in]

Specifies the type of information to be returned in the buffer. Set this parameter to one of the following KEY_VALUE_INFORMATION_CLASS enumeration values:

<ul>
<li>
<b>KeyValueBasicInformation</b>

</li>
<li>
<b>KeyValueFullInformation</b>

</li>
<li>
<b>KeyValuePartialInformation</b>

</li>
</ul>

### -param KeyValueInformation [out]

Pointer to a caller-allocated buffer into which the method writes the requested data. The buffer contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554217">KEY_VALUE_FULL_INFORMATION</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554220">KEY_VALUE_PARTIAL_INFORMATION</a>, depending on the value of <i>KeyValueInformationClass</i>. The structure is followed by additional data whose size depends on the data type of the key value.


### -param Length [in]

Size in bytes of the <i>KeyValueInformation</i> buffer, which the caller must set according to the given <i>KeyValueInformationClass</i>. To receive all the requested data, the buffer must be at least as large as the size of the requested data.


### -param ResultLength [out]

Output pointer for the length of the resulting data. This parameter points to a caller-allocated ULONG variable into which the method writes a count specifying the number of bytes actually written into the <i>KeyValueInformation</i> buffer. If the specified buffer length is too small to contain the information, however, the method instead outputs the required buffer size and returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. For more information, see the following Remarks section.


## -returns



<code>QueryValueKey</code> returns STATUS_SUCCESS if the call was successful in copying the requested information to the <i>KeyValueInformation</i> buffer. If the specified buffer size is too small to receive all of the requested information, the method returns STATUS_BUFFER_OVERFLOW. If the specified buffer size is too small to receive any of the requested information, the method returns STATUS_BUFFER_TOO_SMALL. Otherwise, the method returns an appropriate error status code. The following table shows some of the possible error codes.

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
Indicates that the value entry with the specified name was not found.

</td>
</tr>
</table>
 




## -remarks



If the <i>KeyValueInformation</i> buffer is too small to hold the requested information, the method writes the required size to *<i>ResultLength</i> and returns a status code of either STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. The method returns STATUS_BUFFER_OVERFLOW if it succeeded in writing only part of the requested information to the buffer. The method returns STATUS_BUFFER_TOO_SMALL if it was unable to write any information to the buffer. The value written to *<i>ResultLength</i> indicates the minimum buffer size required to hold all the requested information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554217">KEY_VALUE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554220">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567069">ZwQueryValueKey</a>
 

 

