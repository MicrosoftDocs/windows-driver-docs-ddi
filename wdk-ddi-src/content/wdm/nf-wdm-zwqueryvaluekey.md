---
UID: NF:wdm.ZwQueryValueKey
title: ZwQueryValueKey function
author: windows-driver-content
description: The ZwQueryValueKey routine returns a value entry for a registry key.
old-location: kernel\zwqueryvaluekey.htm
old-project: kernel
ms.assetid: 76efd9c0-933b-4d3a-a936-de852615fb87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwQueryValueKey
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
req.alt-api: ZwQueryValueKey,NtQueryValueKey
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwQueryValueKey function



## -description
The <b>ZwQueryValueKey</b> routine returns a value entry for a registry key.



## -syntax

````
NTSTATUS ZwQueryValueKey(
  _In_      HANDLE                      KeyHandle,
  _In_      PUNICODE_STRING             ValueName,
  _In_      KEY_VALUE_INFORMATION_CLASS KeyValueInformationClass,
  _Out_opt_ PVOID                       KeyValueInformation,
  _In_      ULONG                       Length,
  _Out_     PULONG                      ResultLength
);
````


## -parameters

### -param KeyHandle [in]

Handle to the key to read value entries from. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>. 


### -param ValueName [in]

Pointer to the name of the value entry to obtain data for. 


### -param KeyValueInformationClass [in]

A <a href="..\wdm\ne-wdm-_key_value_information_class.md">KEY_VALUE_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyValueInformation</i> buffer. 


### -param KeyValueInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information.


### -param Length [in]

Specifies the size, in bytes, of the <i>KeyValueInformation</i> buffer. 


### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the key information. If the <b>ZwQueryValueKey</b> routine returns STATUS_SUCCESS, callers can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, callers can use the value of this variable to determine the size of buffer required to hold the key information. 


## -returns
<b>ZwQueryValueKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The registry value was not available. 
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer supplied is too small, and only partial data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer supplied is too small, and no data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>KeyInformationClass</i> parameter is not a valid <b>KEY_VALUE_INFORMATION_CLASS</b> value.

 


## -remarks
The<i> KeyHandle</i> passed to <b>ZwQueryValueKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_key_value_full_information.md">KEY_VALUE_FULL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_key_value_information_class.md">KEY_VALUE_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_key_value_partial_information.md">KEY_VALUE_PARTIAL_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryValueKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

