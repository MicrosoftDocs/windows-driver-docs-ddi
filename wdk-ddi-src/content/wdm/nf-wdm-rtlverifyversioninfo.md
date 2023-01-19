---
UID: NF:wdm.RtlVerifyVersionInfo
title: RtlVerifyVersionInfo function (wdm.h)
description: The RtlVerifyVersionInfo routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["RtlVerifyVersionInfo function"]
ms.keywords: RtlVerifyVersionInfo, RtlVerifyVersionInfo routine [Kernel-Mode Driver Architecture], k109_c0301686-a323-499f-ac04-3bc414b016cd.xml, kernel.rtlverifyversioninfo, wdm/RtlVerifyVersionInfo
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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

## -description

The **RtlVerifyVersionInfo** routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.

## -parameters

### -param VersionInfo [in]

Pointer to an [**RTL_OSVERSIONINFOEXW**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw) structure that specifies the operating system version requirements to compare to the corresponding attributes of the currently running version of the operating system.

### -param TypeMask [in]

Specifies which members of *VersionInfo* to compare with the corresponding attributes of the currently running version of the operating system. *TypeMask* is set to a logical OR of one or more of the following values.

| Value | Corresponding member |
|---|---|
| VER_BUILDNUMBER | **dwBuildNumber** |
| VER_MAJORVERSION | **dwMajorVersion** |
| VER_MINORVERSION | **dwMinorVersion** |
| VER_PLATFORMID | **dwPlatformId** |
| VER_SERVICEPACKMAJOR | **wServicePackMajor** |
| VER_SERVICEPACKMINOR | **wServicePackMinor** |
| VER_SUITENAME | **wSuiteMask** |
| VER_PRODUCT_TYPE | **wProductType** |

### -param ConditionMask [in]

Specifies how to compare each **VersionInfo** member. To set the value of *ConditionMask*, a caller should use the **VER_SET_CONDITION** macro:

```cpp
VER_SET_CONDITION (
        IN OUT  ULONGLONG  ConditionMask,
        IN ULONG  TypeBitMask,
        IN UCHAR  ComparisonType
        );
```

The value of *ConditionMask* is created in the following way:

- Initialize the value of *ConditionMask* to zero.

- Call **VER_SET_CONDITION** once for each *VersionInfo* member   specified by *TypeMask*.

- Set the *TypeBitMask* and *ComparisonType* parameters for each call to **VER_SET_CONDITION** as follows:

#### TypeBitMask

Indicates the *VersionInfo* member for which the comparison type is set. *TypeBitMask* can be one of the following values.

| Value | Corresponding member |
|---|---|
| VER_BUILDNUMBER | **dwBuildNumber** |
| VER_MAJORVERSION | **dwMajorVersion** |
| VER_MINORVERSION | **dwMinorVersion** |
| VER_PLATFORMID | **dwPlatformId** |
| VER_SERVICEPACKMAJOR | **wServicePackMajor** |
| VER_SERVICEPACKMINOR | **wServicePackMinor** |
| VER_SUITENAME | **wSuiteMask** |
| VER_PRODUCT_TYPE | **wProductType** |

#### ComparisonType

Specifies the comparison type that **RtlVerifyVersionInfo** uses to compare the **VersionInfo** member specified by *TypeBitMask* with the corresponding attribute of the currently running operating system.

For all values of *TypeBitMask* other than VER_SUITENAME, *ComparisonType* is set to one of the following values.

| Value | Meaning |
|---|---|
| VER_EQUAL | The current value must be equal to the specified value. |
| VER_GREATER | The current value must be greater than the specified value. |
| VER_GREATER_EQUAL | The current value must be greater than or equal to the specified value. |
| VER_LESS | The current value must be less than the specified value. |
| VER_LESS_EQUAL | The current value must be less than or equal to the specified value. |

If *TypeBitMask* is set to VER_SUITENAME, *ComparisonType* is set to of one the following values.

| Value | Meaning |
|---|---|
| VER_AND | All product suites specified in the **wSuiteMask** member must be present in the current system. |
| VER_OR | At least one of the specified product suites must be present in the current system. |

## -returns

**RtlVerifyVersionInfo** returns one of the following status values:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The specified version matches the currently running version of the operating system. |
| **STATUS_INVALID_PARAMETER** | The input parameters are not valid. |
| **STATUS_REVISION_MISMATCH** | The specified version does not match the currently running version of the operating system. |

## -remarks

**RtlVerifyVersionInfo** enables a driver to easily verify the presence of a required set of operating system attributes. **RtlVerifyVersionInfo** is the kernel-mode equivalent of the user-mode **VerifyVersionInfo** function in the Windows SDK. See the example in the Windows SDK that shows how to verify the system version.

Typically, **RtlVerifyVersionInfo** returns STATUS_SUCCESS only if all comparisons succeed. However, the major version, minor version, and service pack version are tested in a sequential manner in the following way:

- If the major version exceeds the minimum required, then the minor version and service pack version are not tested. For example, if the current major version is 6.0, a test for a system greater than or equal to version 5.1 service pack 1 succeeds. The minor version and service pack version are not tested.

- If the minor version exceeds the minimum required, then the service pack version is not tested. For example, if the current major version is 5.2, a test for a system version greater than or equal to version 5.1 service pack 1 succeeds. The service pack version is not tested.

- If the major service pack version exceeds the minimum required, then the minor service pack version is not tested.

To verify a range of system versions, a driver can call **RtlVerifyVersionInfo** twice, once to verify a lower bound on the system version and once to verify an upper bound on the system version.

## -see-also

[**RTL_OSVERSIONINFOEXW**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw)

[**RTL_OSVERSIONINFOW**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfow)

[RtlGetVersion](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion)
