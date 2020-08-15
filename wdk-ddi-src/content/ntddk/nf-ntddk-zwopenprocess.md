---
UID: NF:ntddk.ZwOpenProcess
title: ZwOpenProcess function (ntddk.h)
description: The ZwOpenProcess routine opens a handle to a process object and sets the access rights to this object.
old-location: kernel\zwopenprocess.htm
tech.root: kernel
ms.assetid: 261d7676-9ce7-4e15-a58f-0439434f202b
ms.date: 04/30/2018
keywords: ["ZwOpenProcess function"]
ms.keywords: NtOpenProcess, ZwOpenProcess, ZwOpenProcess routine [Kernel-Mode Driver Architecture], k111_cf01d6cd-b10e-46b6-9b78-984aac1ef96d.xml, kernel.zwopenprocess, ntddk/NtOpenProcess, ntddk/ZwOpenProcess
f1_keywords:
 - "ntddk/ZwOpenProcess"
 - "ZwOpenProcess"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwOpenProcess
- NtOpenProcess
targetos: Windows
req.typenames: 
---

# ZwOpenProcess function


## -description


The <b>ZwOpenProcess</b> routine opens a handle to a process object and sets the access rights to this object.


## -parameters




### -param ProcessHandle 
[out]
A pointer to a variable of type HANDLE. The <b>ZwOpenProcess</b> routine writes the process handle to the variable that this parameter points to.


### -param DesiredAccess 
[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that contains the access rights that the caller has requested to the process object.


### -param ObjectAttributes 
[in]
A pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the attributes to apply to the process object handle. In Windows Vista and later versions of Windows, the <b>ObjectName</b> field of this structure must be set to <b>NULL</b>. In Windows Server 2003, Windows XP, and Windows 2000, this field can, as an option, point to an object name. For more information, see the following Remarks section.


### -param ClientId 
[in, optional]
A pointer to a client ID that identifies the thread whose process is to be opened. In Windows Vista and later versions of Windows, this parameter must be a non-<b>NULL</b> pointer to a valid client ID. In Windows Server 2003, Windows XP, and Windows 2000, this parameter is optional and can be set to <b>NULL</b> if the <b>OBJECT_ATTRIBUTES</b> structure that <i>ObjectAttributes</i> points to specifies an object name. For more information, see the following Remarks section.


## -returns



<b>ZwOpenProcess</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl>
</td>
<td width="60%">
In Windows Vista and later versions of Windows, the caller either supplied an object name or failed to supply a client ID. In Windows Server 2003, Windows XP, and Windows 2000, the caller supplied both an object name and a client ID.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_CID</b></dt>
</dl>
</td>
<td width="60%">
The specified client ID is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The requested access rights are not valid for a process object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The requested access rights cannot be granted.

</td>
</tr>
</table>
 




## -remarks



In Windows Vista and later versions of Windows, the <i>ClientId</i> parameter must point to a client ID that identifies the thread whose process is to be opened. In addition, the <b>ObjectName</b> field of the structure pointed to by <i>ObjectAttributes</i> must be set to <b>NULL</b>.

In Windows Server 2003, Windows XP, and Windows 2000, the caller has the option of supplying either a client ID or an object name (but not both). If the <b>ObjectName</b> field of the structure pointed to by <i>ObjectAttributes</i> contains a non-<b>NULL</b> pointer to an object name, <i>ClientId</i> must be <b>NULL</b>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenProcess</b>" instead of "<b>ZwOpenProcess</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>
 

 

