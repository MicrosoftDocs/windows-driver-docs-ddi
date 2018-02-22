---
UID: NF:portcls.IRegistryKey.SetValueKey
title: IRegistryKey::SetValueKey method
author: windows-driver-content
description: The SetValueKey method replaces or creates a value entry under the open key.
old-location: audio\iregistrykey_setvaluekey.htm
old-project: audio
ms.assetid: 4f9dd025-b49f-44ab-88c4-38139e6cbee2
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: SetValueKey, IRegistryKey::SetValueKey, portcls/IRegistryKey::SetValueKey, IRegistryKey, SetValueKey method [Audio Devices], IRegistryKey interface, IRegistryKey interface [Audio Devices], SetValueKey method, audmp-routines_a7668b45-2b58-4a49-b1ef-a8d0755225b0.xml, SetValueKey method [Audio Devices], audio.iregistrykey_setvaluekey
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IRegistryKey.SetValueKey
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IRegistryKey::SetValueKey method


## -description


The <code>SetValueKey</code> method replaces or creates a value entry under the open key.


## -syntax


````
NTSTATUS SetValueKey(
  [in, optional] PUNICODE_STRING ValueName,
  [in]           ULONG           Type,
  [in]           PVOID           Data,
  [in]           ULONG           DataSize
);
````


## -parameters




### -param ValueName [in, optional]

Pointer to a string containing the name of the value entry to set. The name string is specified by a structure of type <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>. If the value entry has no name, set this parameter to <b>NULL</b>. If the caller specifies a name string but the given name is not unique relative to its containing key, the method replaces the data for an existing value entry.


### -param Type [in]

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

These parameter types are explained in <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>.


### -param Data [in]

Pointer to a buffer containing the data. This parameter points to a user-supplied structure or value appropriate to the function.


### -param DataSize [in]

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

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>



<a href="..\portcls\nn-portcls-iregistrykey.md">IRegistryKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IRegistryKey::SetValueKey method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

