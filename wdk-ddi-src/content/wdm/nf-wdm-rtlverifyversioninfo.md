---
UID: NF:wdm.RtlVerifyVersionInfo
title: RtlVerifyVersionInfo function (wdm.h)
description: The RtlVerifyVersionInfo routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.
old-location: kernel\rtlverifyversioninfo.htm
tech.root: kernel
ms.assetid: 7c0ca9a0-dfa4-44ab-8d3a-ab43f72c806f
ms.date: 04/30/2018
keywords: ["RtlVerifyVersionInfo function"]
ms.keywords: RtlVerifyVersionInfo, RtlVerifyVersionInfo routine [Kernel-Mode Driver Architecture], k109_c0301686-a323-499f-ac04-3bc414b016cd.xml, kernel.rtlverifyversioninfo, wdm/RtlVerifyVersionInfo
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlVerifyVersionInfo
 - wdm/RtlVerifyVersionInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlVerifyVersionInfo
---

# RtlVerifyVersionInfo function


## -description

The <b>RtlVerifyVersionInfo</b> routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.

## -parameters

### -param VersionInfo 

[in]
Pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a> structure that specifies the operating system version requirements to compare to the corresponding attributes of the currently running version of the operating system.

### -param TypeMask 

[in]
Specifies which members of <i>VersionInfo</i> to compare with the corresponding attributes of the currently running version of the operating system. <i>TypeMask</i> is set to a logical OR of one or more of the following values.
                        

<table>
<tr>
<th>Value</th>
<th>Corresponding member</th>
</tr>
<tr>
<td>
VER_BUILDNUMBER

</td>
<td>
<b>dwBuildNumber</b>

</td>
</tr>
<tr>
<td>
VER_MAJORVERSION

</td>
<td>
<b>dwMajorVersion</b>

</td>
</tr>
<tr>
<td>
VER_MINORVERSION

</td>
<td>
<b>dwMinorVersion</b>

</td>
</tr>
<tr>
<td>
VER_PLATFORMID

</td>
<td>
<b>dwPlatformId</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMAJOR

</td>
<td>
<b>wServicePackMajor</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMINOR

</td>
<td>
<b>wServicePackMinor</b>

</td>
</tr>
<tr>
<td>
VER_SUITENAME

</td>
<td>
<b>wSuiteMask</b>

</td>
</tr>
<tr>
<td>
VER_PRODUCT_TYPE

</td>
<td>
<b>wProductType</b>

</td>
</tr>
</table>

### -param ConditionMask 

[in]
Specifies how to compare each <b>VersionInfo</b> member. To set the value of <i>ConditionMask</i>, a caller should use the <b>VER_SET_CONDITION</b> macro:
						  


```
VER_SET_CONDITION (
        IN OUT  ULONGLONG  ConditionMask,
        IN ULONG  TypeBitMask,
        IN UCHAR  ComparisonType
        );
```

The value of <i>ConditionMask</i> is created in the following way:

<ul>
<li>
Initialize the value of <i>ConditionMask</i> to zero. 

</li>
<li>
Call <b>VER_SET_CONDITION</b> once for each <i>VersionInfo</i> member specified by <i>TypeMask</i>.

</li>
<li>
Set the <i>TypeBitMask</i> and <i>ComparisonType</i> parameters for each call to <b>VER_SET_CONDITION</b> as follows:

</li>
</ul>




#### TypeBitMask

Indicates the <i>VersionInfo</i> member for which the comparison type is set. <i>TypeBitMask</i> can be one of the following values.
        

<table>
<tr>
<th>Value</th>
<th>Corresponding member</th>
</tr>
<tr>
<td>
VER_BUILDNUMBER

</td>
<td>
<b>dwBuildNumber</b>

</td>
</tr>
<tr>
<td>
VER_MAJORVERSION

</td>
<td>
<b>dwMajorVersion</b>

</td>
</tr>
<tr>
<td>
VER_MINORVERSION

</td>
<td>
<b>dwMinorVersion</b>

</td>
</tr>
<tr>
<td>
VER_PLATFORMID

</td>
<td>
<b>dwPlatformId</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMAJOR

</td>
<td>
<b>wServicePackMajor</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMINOR

</td>
<td>
<b>wServicePackMinor</b>

</td>
</tr>
<tr>
<td>
VER_SUITENAME

</td>
<td>
<b>wSuiteMask</b>

</td>
</tr>
<tr>
<td>
VER_PRODUCT_TYPE

</td>
<td>
<b>wProductType</b>

</td>
</tr>
</table>
 



#### ComparisonType

Specifies the comparison type that <b>RtlVerifyVersionInfo</b> uses to compare the <b>VersionInfo</b> member specified by <i>TypeBitMask</i> with the corresponding attribute of the currently running operating system.
        

For all values of <i>TypeBitMask</i> other than VER_SUITENAME, <i>ComparisonType</i> is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_EQUAL

</td>
<td>
The current value must be equal to the specified value.

</td>
</tr>
<tr>
<td>
VER_GREATER

</td>
<td>
The current value must be greater than the specified value.

</td>
</tr>
<tr>
<td>
VER_GREATER_EQUAL

</td>
<td>
The current value must be greater than or equal to the specified value.

</td>
</tr>
<tr>
<td>
VER_LESS

</td>
<td>
The current value must be less than the specified value.

</td>
</tr>
<tr>
<td>
VER_LESS_EQUAL

</td>
<td>
The current value must be less than or equal to the specified value.

</td>
</tr>
</table>
 

If <i>TypeBitMask</i> is set to VER_SUITENAME, <i>ComparisonType</i> is set to of one the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_AND

</td>
<td>
All product suites specified in the <b>wSuiteMask</b> member must be present in the current system.

</td>
</tr>
<tr>
<td>
VER_OR

</td>
<td>
At least one of the specified product suites must be present in the current system.

</td>
</tr>
</table>

## -returns

<b>RtlVerifyVersionInfo</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The specified version matches the currently running version of the operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The input parameters are not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REVISION_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified version does not match the currently running version of the operating system.

</td>
</tr>
</table>

## -remarks

<b>RtlVerifyVersionInfo</b> enables a driver to easily verify the presence of a required set of operating system attributes. <b>RtlVerifyVersionInfo</b> is the kernel-mode equivalent of the user-mode <b>VerifyVersionInfo</b> function in the Windows SDK. See the example in the Windows SDK that shows how to verify the system version.

Typically, <b>RtlVerifyVersionInfo</b> returns STATUS_SUCCESS only if all comparisons succeed. However, the major version, minor version, and service pack version are tested in a sequential manner in the following way:

<ul>
<li>
If the major version exceeds the minimum required, then the minor version and service pack version are not tested. For example, if the current major version is 6.0, a test for a system greater than or equal to version 5.1 service pack 1 succeeds. The minor version and service pack version are not tested.

</li>
<li>
If the minor version exceeds the minimum required, then the service pack version is not tested. For example, if the current major version is 5.2, a test for a system version greater than or equal to version 5.1 service pack 1 succeeds. The service pack version is not tested.

</li>
<li>
If the major service pack version exceeds the minimum required, then the minor service pack version is not tested.

</li>
</ul>
To verify a range of system versions, a driver can call <b>RtlVerifyVersionInfo</b> twice, once to verify a lower bound on the system version and once to verify an upper bound on the system version.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfow">RTL_OSVERSIONINFOW</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a>