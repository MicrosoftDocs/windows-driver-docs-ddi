---
UID: NF:wdm.PcwRegister
title: PcwRegister function (wdm.h)
description: The PcwRegister function registers the caller as a provider of the specified counter set.
old-location: devtest\pcwregister.htm
tech.root: devtest
ms.assetid: 40fdb77c-bd6b-4ecd-a9c8-fd5e5b2adc80
ms.date: 02/23/2018
keywords: ["PcwRegister function"]
ms.keywords: PcwRegister, PcwRegister function [Driver Development Tools], devtest.pcwregister, km_pcw_5204b626-3251-4c63-bd89-be1470980960.xml, wdm/PcwRegister
f1_keywords:
 - "wdm/PcwRegister"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PcwRegister
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcwRegister function

## -description

The `PcwRegister` function creates a new registration of the specified counterset.

## -parameters

### -param Registration [out]

A pointer to a PPCW_REGISTRATION. Receives the handle to the newly allocated registration. The registration should be closed using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwunregister">PcwUnregister</a>.

### -param Info [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pcw_registration_information">`PCW_REGISTRATION_INFORMATION`</a> structure that contains the details about the counter set being registered.

## -returns

This function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td>`STATUS_SUCCESS`</td>
<td>
The counter set is successfully registered.
</td>
</tr>
<tr>
<td>`STATUS_INVALID_PARAMETER_2`</td>
<td>
<p>
The `Info->Name->Length` field is 0 or is not a multiple of `sizeof(WCHAR)`.
</p>
<p>-- OR --</p>
<p>
The `Info->Version` field does not match a supported value for this version of Windows. For Windows versions prior to Windows 10 20H1 (Manganese), the Version must be set to `PCW_VERSION_1` (0x100). For Windows 10 20H1 (Manganese) and later, the Version must be set to `PCW_VERSION_1` (0x100) or `PCW_VERSION_2` (0x200). Use `PCW_CURRENT_VERSION` to automatically use `PCW_VERSION_1` or `PCW_VERSION_2` based on the compile-time value of `NTDDI_VERSION`.
</p>
<p>-- OR --</p>
<p>
The `Info->Flags` field contains a value other than `PcwRegistrationNone` or `PcwRegistrationSiloNeutral`.
</p>
</td>
</tr>
<tr>
<td>`STATUS_INTEGER_OVERFLOW`</td>
<td>
The number of the counters exposed by this registration exceeds the space available.
</td>
</tr>
<tr>
<td>`STATUS_NO_MEMORY`</td>
<td>
There is not enough space available to allocate memory for the counters
</td>
</tr>
</table>

## -remarks

The provider calls this function to create a new counterset registration. The registration is added to the counterset's registration list. All the input arguments are captured so that the caller does not have to keep a copy of them.

By default, the new counterset is visible only to the server silo that was active at the time the registration is created (i.e. `PcwRegister` associates the newly-created registration with the server silo that was attached to the thread at the time the registration is created). On Windows 10 20H1 or later, use the `PcwRegistrationSiloNeutral` flag in the `PCW_REGISTRATION_INFORMATION::Flags` field to create a counterset registration that is visible to all server silos.

If using the `CTRPP` code generation tool, the developer will typically use the CTRPP-generated Register function instead of calling PcwRegister directly. (For additional control over the `Version` and `Flags` fields of the `PCW_REGISTRATION_INFORMATION` structure, use the CTRPP-generated InitRegistrationInformation function and then call `PcwRegister` instead of using the CTRPP-generated Register function.)

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwunregister">PcwUnregister</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pcw_registration_information">PCW_REGISTRATION_INFORMATION</a>