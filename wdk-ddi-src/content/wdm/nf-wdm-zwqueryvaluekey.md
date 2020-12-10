---
UID: NF:wdm.ZwQueryValueKey
title: ZwQueryValueKey function (wdm.h)
description: The ZwQueryValueKey routine returns a value entry for a registry key.
old-location: kernel\zwqueryvaluekey.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwQueryValueKey function"]
ms.keywords: NtQueryValueKey, ZwQueryValueKey, ZwQueryValueKey routine [Kernel-Mode Driver Architecture], k111_f51b0b92-f768-4f96-9f2a-d1322fd02517.xml, kernel.zwqueryvaluekey, wdm/NtQueryValueKey, wdm/ZwQueryValueKey
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwQueryValueKey
 - wdm/ZwQueryValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryValueKey
 - NtQueryValueKey
---

# ZwQueryValueKey function


## -description

The <b>ZwQueryValueKey</b> routine returns a value entry for a registry key.

## -parameters

### -param KeyHandle 

[in]
Handle to the key to read value entries from. This handle is created by a successful call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

### -param ValueName 

[in]
Pointer to the name of the value entry to obtain data for.

### -param KeyValueInformationClass 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyValueInformation</i> buffer.

### -param KeyValueInformation 

[out, optional]
Pointer to a caller-allocated buffer that receives the requested information.

### -param Length 

[in]
Specifies the size, in bytes, of the <i>KeyValueInformation</i> buffer.

### -param ResultLength 

[out]
Pointer to a variable that receives the size, in bytes, of the key information. If the <b>ZwQueryValueKey</b> routine returns STATUS_SUCCESS, callers can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, callers can use the value of this variable to determine the size of buffer required to hold the key information.

## -returns

<b>ZwQueryValueKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value was not available. 

</td>
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
The <i>KeyInformationClass</i> parameter is not a valid <b>KEY_VALUE_INFORMATION_CLASS</b> value.

<div class="alert"><b>Warning</b>    If you specify <b>KeyValueBasicInformation</b> for <i>KeyValueInformationClass</i>, Windows 98 and Windows Me return STATUS_SUCCESS even if the registry key or value name does not exist. </div>
<div> </div>
</td>
</tr>
</table>

## -remarks

The<i> KeyHandle</i> passed to <b>ZwQueryValueKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

For more information about working with registry keys, see <a href="/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtQueryValueKey</b>" instead of "<b>ZwQueryValueKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>
