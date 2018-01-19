---
UID: NF:wdm.RtlWriteRegistryValue
title: RtlWriteRegistryValue function
author: windows-driver-content
description: The RtlWriteRegistryValue routine writes caller-supplied data into the registry along the specified relative path at the given value name.
old-location: kernel\rtlwriteregistryvalue.htm
old-project: kernel
ms.assetid: 97bcd205-ffc0-4645-87d4-659651ed579a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlWriteRegistryValue
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
req.alt-api: RtlWriteRegistryValue
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlWriteRegistryValue function



## -description
The <b>RtlWriteRegistryValue</b> routine writes caller-supplied data into the registry along the specified relative path at the given value name.



## -syntax

````
NTSTATUS RtlWriteRegistryValue(
  _In_     ULONG  RelativeTo,
  _In_     PCWSTR Path,
  _In_     PCWSTR ValueName,
  _In_     ULONG  ValueType,
  _In_opt_ PVOID  ValueData,
  _In_     ULONG  ValueLength
);
````


## -parameters

### -param RelativeTo [in]

Specifies whether <i>Path</i> is an absolute registry path or is relative to a predefined path as one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RTL_REGISTRY_ABSOLUTE

</td>
<td>
Path is an absolute registry path.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_SERVICES

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Services</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_CONTROL

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Control</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_WINDOWS_NT

</td>
<td>
Path is relative to <b>\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_DEVICEMAP

</td>
<td>
Path is relative to <b>\Registry\Machine\Hardware\DeviceMap</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_USER

</td>
<td>
Path is relative to <b>\Registry\User\CurrentUser</b>. (For a system process, this is <b>\Users\.Default</b>.)

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_OPTIONAL

</td>
<td>
Specifies that the key referenced by this parameter and the <i>Path</i> parameter are optional.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_HANDLE

</td>
<td>
Specifies that the <i>Path</i> parameter is actually a registry handle to use. This value is optional.

</td>
</tr>
</table>
 


### -param Path [in]

Pointer to either an absolute registry path or a path relative to the known location specified by the <i>RelativeTo</i> parameter. If the RTL_REGISTRY_HANDLE flag is specified, this parameter is a registry handle for an already opened key to be used directly.


### -param ValueName [in]

Pointer to the name of a subkey or value entry to be written into the registry.


### -param ValueType [in]

Specifies a REG_<i>XXX</i> value that determines the type of the <i>ValueName</i> parameter. For a list of the possible values, see the <i>Type</i> parameter of <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>.


### -param ValueData [in, optional]

Pointer to the name of a subkey or values for its value entries (or both) to be written into the registry.


### -param ValueLength [in]

Specifies the number of bytes of <i>ValueData</i> to be written into the registry.


## -returns
<b>RtlWriteRegistryValue</b> returns the status of the operation, either STATUS_SUCCESS or an error status.


## -remarks
If the specified key does not exist, the routine attempts to create the key. For this attempt to succeed, the new key must be a direct subkey of the key that is referred to by the <i>Path</i> parameter, and the key that <i>Path</i> refers to must have been opened for KEY_CREATE_SUB_KEY access.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlcheckregistrykey.md">RtlCheckRegistryKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcreateregistrykey.md">RtlCreateRegistryKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtldeleteregistryvalue.md">RtlDeleteRegistryValue</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlWriteRegistryValue routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

