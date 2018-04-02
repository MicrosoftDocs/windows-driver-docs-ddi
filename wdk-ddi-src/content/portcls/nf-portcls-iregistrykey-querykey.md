---
UID: NF:portcls.IRegistryKey.QueryKey
title: IRegistryKey::QueryKey method
author: windows-driver-content
description: The QueryKey method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes.
old-location: audio\iregistrykey_querykey.htm
old-project: audio
ms.assetid: 1b2642da-1b04-49a8-942e-6eb93afd12f2
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IRegistryKey, IRegistryKey interface [Audio Devices], QueryKey method, IRegistryKey::QueryKey, QueryKey method [Audio Devices], QueryKey method [Audio Devices], IRegistryKey interface, QueryKey,IRegistryKey.QueryKey, audio.iregistrykey_querykey, audmp-routines_88fe19d0-095e-4f70-b8aa-a0c908600296.xml, portcls/IRegistryKey::QueryKey
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
-	IRegistryKey.QueryKey
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IRegistryKey::QueryKey method


## -description


The <code>QueryKey</code> method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes.


## -parameters




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

Pointer to a caller-allocated buffer into which the method writes the requested data. The buffer holds a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>, depending on the value of <i>KeyInformationClass</i>. The structure is followed by a string of Unicode characters whose size depends on the type of information being requested about the key and the length of the key's name or class string.


### -param Length [in]

Size in bytes of the <i>KeyInformation</i> buffer, which the caller must set according to the given <i>KeyInformationClass</i>. To receive all the requested data, the buffer must be at least as large as the size of the requested data.


### -param ResultLength [out]

Output pointer for the length of the resulting data. This parameter points to a caller-allocated ULONG variable into which the method writes a count specifying the number of bytes actually written into the <i>KeyInformation</i> buffer. If the specified buffer length is too small to contain the information, however, the method instead outputs the required buffer size and returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. For more information, see the following Remarks section.


## -returns



<code>QueryKey</code> returns STATUS_SUCCESS if the call was successful in copying the requested information to the <i>KeyInformation</i> buffer. If the specified buffer size is too small to receive all of the requested information, the method returns STATUS_BUFFER_OVERFLOW. If the specified buffer size is too small to receive any of the requested information, the method returns STATUS_BUFFER_TOO_SMALL. Otherwise, the method returns an appropriate error status code. The following table shows some of the possible error codes.

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
</table>
 




## -remarks



If the <i>KeyInformation</i> buffer is too small to hold the requested information, the method writes the required size to *<i>ResultLength</i> and returns a status code of either STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. The method returns STATUS_BUFFER_OVERFLOW if it succeeded in writing only part of the requested information to the buffer. The method returns STATUS_BUFFER_TOO_SMALL if it was unable to write any information to the buffer. The value written to *<i>ResultLength</i> indicates the minimum buffer size required to hold all the requested information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

