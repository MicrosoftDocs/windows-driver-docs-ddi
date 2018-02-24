---
UID: NF:portcls.IRegistryKey.EnumerateKey
title: IRegistryKey::EnumerateKey method
author: windows-driver-content
description: The EnumerateKey method returns information about the subkeys of the open key.
old-location: audio\iregistrykey_enumeratekey.htm
old-project: audio
ms.assetid: 2438c994-a283-49fe-a39b-99de678df2e2
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: audmp-routines_ef31b848-c963-4327-ba86-bca98383ad90.xml, EnumerateKey method [Audio Devices], IRegistryKey, EnumerateKey method [Audio Devices], IRegistryKey interface, IRegistryKey interface [Audio Devices], EnumerateKey method, IRegistryKey::EnumerateKey, audio.iregistrykey_enumeratekey, portcls/IRegistryKey::EnumerateKey, EnumerateKey
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
-	IRegistryKey.EnumerateKey
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IRegistryKey::EnumerateKey method


## -description


The <code>EnumerateKey</code> method returns information about the subkeys of the open key.


## -syntax


````
NTSTATUS EnumerateKey(
  [in]  ULONG                 Index,
  [in]  KEY_INFORMATION_CLASS KeyInformationClass,
  [out] PVOID                 KeyInformation,
  [in]  ULONG                 Length,
  [out] PULONG                ResultLength
);
````


## -parameters




### -param Index [in]

Specifies the subkey index. This parameter identifies the subkey for which key information is requested. If the key contains <i>n</i> subkeys, valid indices range from 0 to <i>n</i>-1. If the index exceeds this range, the method returns STATUS_NO_MORE_ENTRIES.


### -param KeyInformationClass [in]

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

### -param KeyInformation [out]

Pointer to the key information buffer. This parameter points to a caller-allocated buffer into which the method writes the requested data. The buffer contains a structure of type <a href="..\wdm\ns-wdm-_key_basic_information.md">KEY_BASIC_INFORMATION</a>, <a href="..\wdm\ns-wdm-_key_full_information.md">KEY_FULL_INFORMATION</a>, or <a href="..\wdm\ns-wdm-_key_node_information.md">KEY_NODE_INFORMATION</a>, depending on the value of <i>KeyInformationClass</i>. The structure is followed by a string of Unicode characters whose size depends on the type of information being requested about the key.


### -param Length [in]

Specifies the size in bytes of the <i>KeyInformation</i> buffer, which the caller must set according to the given <i>KeyInformationClass</i>. For the call to succeed, the buffer must be at least as large as the data that the method writes into the buffer.


### -param ResultLength [out]

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

<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>



<a href="..\wdm\ns-wdm-_key_basic_information.md">KEY_BASIC_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_node_information.md">KEY_NODE_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_full_information.md">KEY_FULL_INFORMATION</a>



<a href="..\portcls\nn-portcls-iregistrykey.md">IRegistryKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IRegistryKey::EnumerateKey method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

