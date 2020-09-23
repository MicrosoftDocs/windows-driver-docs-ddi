---
UID: NF:wdm.ZwDeleteValueKey
title: ZwDeleteValueKey function (wdm.h)
description: The ZwDeleteValueKey routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned.
old-location: kernel\zwdeletevaluekey.htm
tech.root: kernel
ms.assetid: e7fc9290-8f24-4b9f-822a-0bdce50dafb9
ms.date: 04/30/2018
keywords: ["ZwDeleteValueKey function"]
ms.keywords: NtDeleteValueKey, ZwDeleteValueKey, ZwDeleteValueKey routine [Kernel-Mode Driver Architecture], k111_81ff5c8c-442c-4ddd-9166-5445b964893a.xml, kernel.zwdeletevaluekey, wdm/NtDeleteValueKey, wdm/ZwDeleteValueKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwDeleteValueKey
 - wdm/ZwDeleteValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwDeleteValueKey
 - NtDeleteValueKey
---

# ZwDeleteValueKey function


## -description

The <b>ZwDeleteValueKey</b> routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned.

## -parameters

### -param KeyHandle 

[in]
The handle to the registry key containing the value entry of interest. This key must have been opened with KEY_SET_VALUE set for the desired access. This handle is created by a successful call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

### -param ValueName 

[in]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the value entry to delete. This parameter can be an empty string if the value entry has no name.

## -returns

<b>ZwDeleteValueKey</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The <i>KeyHandle</i> handle does not have the KEY_SET_VALUE access. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Additional resources required by this function were not available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>KeyHandle</i> parameter was a <b>NULL</b> pointer or not a valid pointer to an open registry key. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>ValueName</i> registry key entry was not found. 

</td>
</tr>
</table>

## -remarks

The <i>KeyHandle</i> passed to <b>ZwDeleteValueKey</b> must have been opened for delete access to succeed. The <i>DesiredAccess</i> values of KEY_SET_VALUE, KEY_WRITE, and KEY_ALL_ACCESS include the KEY_SET_VALUE access mask required for delete access. For a description of possible values for <i>DesiredAccess</i>, see <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>.

If callback functions are registered for this registry key, then these callback functions will be called.

Device drivers should not attempt to call <b>ZwDeleteValueKey</b> directly to delete value entries in a subkey of the <b>\Registry..\ResourceMap</b> key. Only the system can write or delete value entries in the <b>\Registry..\HardwareDescription</b> tree.

<div class="alert"><b>Note</b>    If the call to this function occurs in user mode, you should use the name "<b>NtDeleteValueKey</b>" instead of "<b>ZwDeleteValueKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletekey">ZwDeleteKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>