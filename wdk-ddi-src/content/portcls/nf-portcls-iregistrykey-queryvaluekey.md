---
UID: NF:portcls.IRegistryKey.QueryValueKey
title: IRegistryKey::QueryValueKey method
author: windows-driver-content
description: The QueryValueKey method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.
old-location: audio\iregistrykey_queryvaluekey.htm
old-project: audio
ms.assetid: 6339a8bf-ab32-48bc-aae6-2cce2a6a648d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IRegistryKey, IRegistryKey interface [Audio Devices], QueryValueKey method, IRegistryKey::QueryValueKey, QueryValueKey method [Audio Devices], QueryValueKey method [Audio Devices], IRegistryKey interface, QueryValueKey,IRegistryKey.QueryValueKey, audio.iregistrykey_queryvaluekey, audmp-routines_2b41aa08-8b71-45af-bcfa-c33723c82c13.xml, portcls/IRegistryKey::QueryValueKey
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
req.lib: portcls.h
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
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IRegistryKey::QueryValueKey method


## -description


The <code>QueryValueKey</code> method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.


## -syntax


````
NTSTATUS QueryValueKey(
  [in]  PUNICODE_STRING             ValueName,
  [in]  KEY_VALUE_INFORMATION_CLASS KeyValueInformationClass,
  [out] PVOID                       KeyValueInformation,
  [in]  ULONG                       Length,
  [out] PULONG                      ResultLength
);
````


## -parameters




### -param ValueName [in]

Pointer to the manufacturer-supplied name of the value entry. The name string is specified by a structure of type <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>.


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

Pointer to a caller-allocated buffer into which the method writes the requested data. The buffer contains a structure of type <a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>, <a href="..\wdm\ns-wdm-_key_value_full_information.md">KEY_VALUE_FULL_INFORMATION</a>, or <a href="..\wdm\ns-wdm-_key_value_partial_information.md">KEY_VALUE_PARTIAL_INFORMATION</a>, depending on the value of <i>KeyValueInformationClass</i>. The structure is followed by additional data whose size depends on the data type of the key value.


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

<a href="..\wdm\ns-wdm-_key_value_partial_information.md">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>



<a href="..\wdm\ns-wdm-_key_value_full_information.md">KEY_VALUE_FULL_INFORMATION</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\portcls\nn-portcls-iregistrykey.md">IRegistryKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IRegistryKey::QueryValueKey method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

