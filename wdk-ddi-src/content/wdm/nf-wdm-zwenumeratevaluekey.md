---
UID: NF:wdm.ZwEnumerateValueKey
title: ZwEnumerateValueKey function (wdm.h)
description: The ZwEnumerateValueKey routine gets information about the value entries of an open key.
old-location: kernel\zwenumeratevaluekey.htm
tech.root: kernel
ms.assetid: 4e94c9cc-eaa9-4de1-8f17-d24a5ed19507
ms.date: 04/30/2018
keywords: ["ZwEnumerateValueKey function"]
ms.keywords: NtEnumerateValueKey, ZwEnumerateValueKey, ZwEnumerateValueKey routine [Kernel-Mode Driver Architecture], k111_bea1b1ab-2cfe-4d17-abd3-1a45652c70a5.xml, kernel.zwenumeratevaluekey, wdm/NtEnumerateValueKey, wdm/ZwEnumerateValueKey
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
 - ZwEnumerateValueKey
 - wdm/ZwEnumerateValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwEnumerateValueKey
 - NtEnumerateValueKey
---

# ZwEnumerateValueKey function


## -description

The <b>ZwEnumerateValueKey</b> routine gets information about the value entries of an open key.

## -parameters

### -param KeyHandle 

[in]
Handle to the registry key that you want to enumerate value entries for. A successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a> creates this handle.

### -param Index 

[in]
The zero-based index of the subkey that you want value information for.

### -param KeyValueInformationClass 

[in]
Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyValueInformation</i> buffer.

### -param KeyValueInformation 

[out, optional]
Pointer to a caller-allocated buffer that receives the requested information.

### -param Length 

[in]
Specifies the size, in bytes, of the <i>KeyValueInformation</i> buffer.

### -param ResultLength 

[out]
Pointer to a variable that receives the size, in bytes, of the value information. If this routine returns STATUS_SUCCESS, the variable indicates the amount of data returned. If this routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, the variable indicates the buffer size that is required to hold the value information.

## -returns

<b>ZwEnumerateValueKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:

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
The <i>KeyInformationClass</i> parameter is not a valid KEY_VALUE_INFORMATION_CLASS value. 

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

The<i> KeyHandle</i> passed to <b>ZwEnumerateValueKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

The <i>Index</i> is simply a way to select among subkeys with value entries. Two calls to <b>ZwEnumerateValueKey</b> with the same <i>Index</i> are not guaranteed to return the same results.

For more information about working with registry keys, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>   If the call to this function occurs in user mode, you should use the name "<b>NtEnumerateValueKey</b>" instead of "<b>ZwEnumerateValueKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a>

