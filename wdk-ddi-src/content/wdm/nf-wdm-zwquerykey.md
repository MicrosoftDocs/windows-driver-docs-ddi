---
UID: NF:wdm.ZwQueryKey
title: ZwQueryKey function
author: windows-driver-content
description: The ZwQueryKey routine provides information about the class of a registry key, and the number and sizes of its subkeys.
old-location: kernel\zwquerykey.htm
tech.root: kernel
ms.assetid: 3b2d3a8b-a21f-4067-a1f0-9aa66c1973f5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtQueryKey, ZwQueryKey, ZwQueryKey routine [Kernel-Mode Driver Architecture], k111_38d7961f-09a3-479c-ba19-ccda00ce5d29.xml, kernel.zwquerykey, wdm/NtQueryKey, wdm/ZwQueryKey
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
-	ZwQueryKey
-	NtQueryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryKey function


## -description


The <b>ZwQueryKey</b> routine provides information about the class of a registry key, and the number and sizes of its subkeys.


## -parameters




### -param KeyHandle [in]

Handle to the registry key to obtain information about. This handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>. 


### -param KeyInformationClass [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyInformation</i> buffer. 


### -param KeyInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information.


### -param Length [in]

Specifies the size, in bytes, of the <i>KeyInformation</i> buffer. 


### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the requested key information. If <b>ZwQueryKey</b> returns STATUS_SUCCESS, the variable contains the amount of data returned. If <b>ZwQueryKey</b> returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of the variable to determine the required buffer size. 


## -returns



<b>ZwQueryKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:

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
The <i>KeyInformationClass</i> parameter is not a valid <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a> value. 

</td>
</tr>
</table>
 




## -remarks



The<i> KeyHandle</i> passed to <b>ZwQueryKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>.
> If _KeyInformationClass_ is KeyNameInformation or KeyHandleTagsInformation, the KEY_QUERY_VALUE requirement does not apply.

<b>ZwQueryKey</b> can be used to obtain information that you can use to allocate buffers to hold registry data, such as the maximum size of a key's value entries or subkey names, or the number of subkeys. For example, you can call <b>ZwQueryKey</b>, use the returned information to allocate a buffer for a subkey, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> to get the name of the subkey, and pass that name to an <b>Rtl</b><b><i>Xxx</i></b><b>Registry</b> routine.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtQueryKey</b>" instead of "<b>ZwQueryKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
 

 

