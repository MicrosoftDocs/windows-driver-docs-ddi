---
UID: NS:wdm._OSVERSIONINFOEXW
title: OSVERSIONINFOEXW (wdm.h)
description: The RTL_OSVERSIONINFOEXW structure contains operating system version information.
tech.root: kernel
ms.date: 12/16/2022
keywords: ["OSVERSIONINFOEXW structure"]
ms.keywords: "*LPOSVERSIONINFOEXW, *POSVERSIONINFOEXW, *PRTL_OSVERSIONINFOEXW, OSVERSIONINFOEX, OSVERSIONINFOEXW, PRTL_OSVERSIONINFOEXW, PRTL_OSVERSIONINFOEXW structure pointer [Kernel-Mode Driver Architecture], RTL_OSVERSIONINFOEXW, RTL_OSVERSIONINFOEXW structure [Kernel-Mode Driver Architecture], _OSVERSIONINFOEXW, kernel.rtl_osversioninfoexw, kstruct_d_a7e48147-5619-4ab4-b83a-18139aa0a2c5.xml, wdm/PRTL_OSVERSIONINFOEXW, wdm/RTL_OSVERSIONINFOEXW"
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: OSVERSIONINFOEXW, *POSVERSIONINFOEXW, *LPOSVERSIONINFOEXW, RTL_OSVERSIONINFOEXW, *PRTL_OSVERSIONINFOEXW
f1_keywords:
 - _OSVERSIONINFOEXW
 - wdm/_OSVERSIONINFOEXW
 - POSVERSIONINFOEXW
 - wdm/POSVERSIONINFOEXW
 - OSVERSIONINFOEXW
 - wdm/OSVERSIONINFOEXW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _OSVERSIONINFOEXW
 - POSVERSIONINFOEXW
 - OSVERSIONINFOEXW
---

## -description

The **RTL_OSVERSIONINFOEXW** structure contains operating system version information.

## -struct-fields

### -field dwOSVersionInfoSize

The size, in bytes, of an **RTL_OSVERSIONINFOEXW** structure. This member must be set before the structure is used with [RtlGetVersion](./nf-wdm-rtlgetversion.md).

### -field dwMajorVersion

The major version number of the operating system. For example, for Windows 2000, the major version number is five. For more information, see the table in Remarks.

### -field dwMinorVersion

The minor version number of the operating system. For example, for Windows 2000, the minor version number is zero. For more information, see the table in Remarks.

### -field dwBuildNumber

The build number of the operating system.

### -field dwPlatformId

The operating system platform. For Win32 on NT-based operating systems, **RtlGetVersion** returns the value VER_PLATFORM_WIN32_NT.

### -field szCSDVersion

The service-pack version string. This member contains a null-terminated string, such as "Service Pack 3", which indicates the latest service pack installed on the system. If no service pack is installed, **RtlGetVersion** might not initialize this string. Initialize *szCSDVersion* to zero (empty string) before the call to **RtlGetVersion**.

### -field wServicePackMajor

The major version number of the latest service pack installed on the system. For example, for Service Pack 3, the major version number is three. If no service pack has been installed, the value is zero.

### -field wServicePackMinor

The minor version number of the latest service pack installed on the system. For example, for Service Pack 3, the minor version number is zero.

### -field wSuiteMask

The product suites available on the system. This member is set to zero or to the bitwise OR of one or more of the following values.

| Value | Meaning |
|---|---|
| VER_SUITE_BACKOFFICE | Microsoft BackOffice components are installed. |
| VER_SUITE_BLADE | Windows Server 2003, Web Edition is installed. |
| VER_SUITE_COMPUTE_SERVER | Windows Server 2003, Compute Cluster Edition is installed. |
| VER_SUITE_DATACENTER | Windows Server 2008 Datacenter, Windows Server 2003, Datacenter Edition, or Windows 2000 Datacenter Server is installed. |
| VER_SUITE_ENTERPRISE | Windows Server 2008 Enterprise, Windows Server 2003, Enterprise Edition, or Windows 2000 Advanced Server is installed. |
| VER_SUITE_EMBEDDEDNT | Windows XP Embedded is installed. |
| VER_SUITE_PERSONAL | Windows Vista Home Premium, Windows Vista Home Basic, or Windows XP Home Edition is installed. |
| VER_SUITE_SINGLEUSERTS | Remote Desktop is supported, but only one interactive session is supported. This value is set unless the system is running in application server mode. |
| VER_SUITE_SMALLBUSINESS (see note) | Microsoft Small Business Server was once installed on the system, but may have been upgraded to another version of Windows. For more information about this flag bit, see the following Remarks section. |
| VER_SUITE_SMALLBUSINESS_RESTRICTED | Microsoft Small Business Server is installed with the restrictive client license in force. For more information about this flag bit, see the following Remarks section. |
| VER_SUITE_STORAGE_SERVER | Windows Storage Server 2003 R2 or Windows Storage Server 2003 is installed. |
| VER_SUITE_TERMINAL | Terminal Services is installed. This value is always set. If VER_SUITE_TERMINAL is set but VER_SUITE_SINGLEUSERTS is not set, the operating system is running in application server mode. |
| VER_SUITE_WH_SERVER | Windows Home Server is installed. |

You should not rely solely on the VER_SUITE_SMALLBUSINESS flag to determine whether Small Business Server is currently installed. Both this flag and the VER_SUITE_SMALLBUSINESS_RESTRICTED flag are set when this product suite is installed. If you upgrade this installation to Windows Server, Standard Edition, the VER_SUITE_SMALLBUSINESS_RESTRICTED flag is cleared, but the VER_SUITE_SMALLBUSINESS flag remains set, which, in this case, indicates that Small Business Server was previously installed on this system. If this installation is further upgraded to Windows Server, Enterprise Edition, the VER_SUITE_SMALLBUSINESS flag remains set.

### -field wProductType

The product type. This member contains additional information about the system. This member can be one of the following values:

| Value | Meaning |
|---|---|
| VER_NT_WORKSTATION | Windows 2000 or later professional version |
| VER_NT_DOMAIN_CONTROLLER | Windows 2000 or later domain controller |
| VER_NT_SERVER | Windows 2000 or later server |

### -field wReserved

Reserved for future use.

## -remarks

The information in this structure includes the major and minor version numbers, the build number, the platform identifier, the installed product suites, and the latest service pack that is installed on the system. This structure is used with the [RtlGetVersion](./nf-wdm-rtlgetversion.md) and [RtlVerifyVersionInfo](./nf-wdm-rtlverifyversioninfo.md) routines.

Relying on version information is not always the best way to test whether a feature is available. For guidance, refer to the documentation for the feature you are interested in.

If possible, design the version detection code in your driver to enable the driver to run on future versions of Windows. If your driver requires a particular operating system version, be sure to treat this version as the minimum supported version, and not as the only version on which the driver can run.

The following table summarizes the version information that is returned by supported versions of Windows. Use the information in the "Other" column or build number to distinguish between operating systems with identical version numbers.

| Operating system | Version number | dwMajorVersion | dwMinorVersion | Other |
|---|---|---|---|---|
| Windows 11 | 10.0 | 10 | 0 | **wProductType** == VER_NT_WORKSTATION |
| Windows Server 2022 | 10.0 | 10 | 0 | **wProductType** != VER_NT_WORKSTATION |
| Windows Server 2019 | 10.0 | 10 | 0 | **wProductType** != VER_NT_WORKSTATION |
| Windows 10 (all releases) | 10.0 | 10 | 0 | **wProductType** == VER_NT_WORKSTATION |
| Windows Server 2016 | 10.0 | 10 | 0 | **wProductType** != VER_NT_WORKSTATION |
| Windows Server 2012 R2 | 6.3 | 6 | 3 | **wProductType** != VER_NT_WORKSTATION |
| Windows 8.1 | 6.3 | 6 | 3 | **wProductType** == VER_NT_WORKSTATION |
| Windows 8 | 6.2 | 6 | 2 | **wProductType** == VER_NT_WORKSTATION |
| Windows Server 2012 | 6.2 | 6 | 2 | **wProductType** != VER_NT_WORKSTATION |
| Windows 7 | 6.1 | 6 | 1 | **wProductType** == VER_NT_WORKSTATION |
| Windows Server 2008 R2 | 6.1 | 6 | 1 | **wProductType** != VER_NT_WORKSTATION |
| Windows Server 2008 | 6.0 | 6 | 0 | **wProductType** != VER_NT_WORKSTATION |
| Windows Vista | 6.0 | 6 | 0 | **wProductType** == VER_NT_WORKSTATION |
| Windows Home Server | 5.2 | 5 | 2 | **wSuiteMask** == VER_SUITE_WH_SERVER |
| Windows Server 2003 | 5.2 | 5 | 2 | Not applicable |
| Windows XP Professional x64 Edition (see note) | 5.2 | 5 | 2 | **wProductType** == VER_NT_WORKSTATION |
| Windows XP | 5.1 | 5 | 1 | Not applicable |
| Windows 2000 | 5.0 | 5 | 0 | Not applicable |

Only a 64-bit kernel-mode driver can run on Windows XP Professional x64 Edition. Therefore, a 32-bit kernel-mode driver can safely omit checking for this version of Windows.

## -see-also

[**RTL_OSVERSIONINFOW**](./ns-wdm-_osversioninfow.md)

[RtlGetVersion](./nf-wdm-rtlgetversion.md)

[RtlVerifyVersionInfo](./nf-wdm-rtlverifyversioninfo.md)