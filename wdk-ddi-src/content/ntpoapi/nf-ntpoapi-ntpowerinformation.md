---
UID: NF:ntpoapi.NtPowerInformation
title: NtPowerInformation function (ntpoapi.h)
description: The ZwPowerInformation routine sets or retrieves system power information.
old-location: kernel\zwpowerinformation.htm
tech.root: kernel
ms.assetid: BA1D5AD2-E3E5-42CB-8E77-627B23078F80
ms.date: 04/30/2018
keywords: ["NtPowerInformation function"]
ms.keywords: NtPowerInformation, PlatformInformation, ZwPowerInformation, ZwPowerInformation routine [Kernel-Mode Driver Architecture], kernel.zwpowerinformation, wdm/NtPowerInformation, wdm/ZwPowerInformation
req.header: ntpoapi.h
req.include-header: Wdm.h, Ntddk.h, Ntpoapi.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.lib
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NtPowerInformation
 - ntpoapi/NtPowerInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.lib
api_name:
 - ZwPowerInformation
 - NtPowerInformation
---

# NtPowerInformation function


## -description

The <b>ZwPowerInformation</b> routine sets or retrieves system power information.

## -parameters

### -param InformationLevel 

[in]
Specifies the requested information level, which indicates the specific power information to be set or retrieved. Currently, the only supported <i>POWER_INFORMATION_LEVEL</i> value is <b>PlatformInformation</b>.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PlatformInformation"></a><a id="platforminformation"></a><a id="PLATFORMINFORMATION"></a><dl>
<dt><b>PlatformInformation</b></dt>
</dl>
</td>
<td width="60%">
Information represents the currently supported power capabilities of the system. Information may change as drivers are installed. For example, the installation of legacy device drivers that do not support power management might modify the capabilities of the system.

</td>
</tr>
</table>

### -param InputBuffer 

[in, optional]
Pointer to a caller-allocated input buffer. This parameter must be <b>NULL</b>, otherwise <b>ERROR_INVALID_PARAMETER</b> is returned.

### -param InputBufferLength 

[in]
Size, in bytes, of the buffer at <i>InputBuffer</i>. The parameter must be set to zero.

### -param OutputBuffer 

[out, optional]
A pointer to an output buffer. The data type of this buffer depends on the information level requested in the <i>InformationLevel</i> parameter. For the <b>PlatformInformation</b> level, the only currently supported value, the <i>OutputBuffer </i> parameter is required and should be of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_platform_information">POWER_PLATFORM_INFORMATION</a> type.

### -param OutputBufferLength 

[in]
Size, in bytes, of the output buffer. Depending on the information level requested, the buffer may be variably sized. <i>PlatformInformation</i>, the only currently supported value, requires a buffer that is the size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_platform_information">POWER_PLATFORM_INFORMATION</a> structure.

## -returns

Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer is of insufficient size to contain the data being returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>PlatformInformation</b> information level, which is the only currently supported value, requires no input buffer and must contain an output buffer. The caller either supplied an input buffer or no output buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller had insufficient access rights to perform the requested action.

</td>
</tr>
</table>

## -remarks

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntpowerinformation">NtPowerInformation</a> and <b>ZwPowerInformation</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.


#### Examples

This example illustrates a valid function call.


```cpp
POWER_PLATFORM_INFORMATION PlatformInfo = {0};
NTSTATUS Result = NtPowerInformation(PlatformInformation, NULL, 0, &PlatformInfo, sizeof(PlatformInfo));

```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_platform_information">POWER_PLATFORM_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>

