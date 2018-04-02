---
UID: NF:wdm.ZwEnumerateKey
title: ZwEnumerateKey function
author: windows-driver-content
description: The ZwEnumerateKey routine returns information about a subkey of an open registry key.
old-location: kernel\zwenumeratekey.htm
old-project: kernel
ms.assetid: 77ccd451-40c7-4f64-af2b-480e44e7f672
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: NtEnumerateKey, ZwEnumerateKey, ZwEnumerateKey routine [Kernel-Mode Driver Architecture], k111_a41e7865-8cac-4dd8-83fb-ca04485feb48.xml, kernel.zwenumeratekey, wdm/NtEnumerateKey, wdm/ZwEnumerateKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwEnumerateKey
-	NtEnumerateKey
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwEnumerateKey function


## -description


The <b>ZwEnumerateKey</b> routine returns information about a subkey of an open registry key.


## -parameters




### -param KeyHandle [in]

Handle to the registry key that contains the subkeys to be enumerated. The handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>. 


### -param Index [in]

The index of the subkey that you want information for. If the key has <i>n</i> subkeys, the subkeys are numbered from 0 to <i>n</i>-1. 


### -param KeyInformationClass [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a> enumeration value that determines the type of information to be received by the <i>KeyInformation</i> buffer. Set <i>KeyInformationClass</i> to one of the following values:

<ul>
<li><b>KeyBasicInformation</b></li>
<li><b>KeyFullInformation</b></li>
<li><b>KeyNodeInformation</b></li>
</ul>
If any value not in this list is specified, the routine returns error code STATUS_INVALID_PARAMETER.


### -param KeyInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information. The <i>KeyInformationClass</i> parameter determines the type of information provided. 


### -param Length [in]

Specifies the size, in bytes, of the <i>KeyInformation</i> buffer. 


### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the registry-key information. If <b>ZwEnumerateKey</b> returns STATUS_SUCCESS, you can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of this variable to determine the size of buffer required to hold the key information. 


## -returns



<b>ZwEnumerateKey</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error code values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer supplied is too small, and only partial data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer supplied is too small, and no data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>KeyInformationClass</i> parameter is not a valid KEY_INFORMATION_CLASS value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
The <i>Index</i> value is out of range for the registry key specified by <i>KeyHandle</i>. For example, if a key has <i>n</i> subkeys, then for any value greater than <i>n</i>-1 the routine returns STATUS_NO_MORE_ENTRIES. 

</td>
</tr>
</table>
 




## -remarks



The handle must have been opened with KEY_ENUMERATE_SUB_KEYS access. This is accomplished by passing KEY_ENUMERATE_SUB_KEYS, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>.

The <i>Index</i> parameter is simply a way to select among subkeys of the key referred to by the <i>KeyHandle</i>. Two calls to <b>ZwEnumerateKey</b> with the same <i>Index</i> are not guaranteed to return the same result.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtEnumerateKey</b>" instead of "<b>ZwEnumerateKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561754">RtlCheckRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561822">RtlCreateRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561829">RtlDeleteRegistryValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562046">RtlQueryRegistryValues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563034">RtlWriteRegistryValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566453">ZwEnumerateValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
 

 

