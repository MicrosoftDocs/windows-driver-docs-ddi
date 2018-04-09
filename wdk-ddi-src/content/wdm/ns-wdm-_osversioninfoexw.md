---
UID: NS:wdm._OSVERSIONINFOEXW
title: "_OSVERSIONINFOEXW"
author: windows-driver-content
description: The RTL_OSVERSIONINFOEXW structure contains operating system version information.
old-location: kernel\rtl_osversioninfoexw.htm
old-project: kernel
ms.assetid: 88471e00-4913-44fd-b9f4-960ec46fb75a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*LPOSVERSIONINFOEXW, *POSVERSIONINFOEXW, *PRTL_OSVERSIONINFOEXW, OSVERSIONINFOEX, OSVERSIONINFOEXW, PRTL_OSVERSIONINFOEXW, PRTL_OSVERSIONINFOEXW structure pointer [Kernel-Mode Driver Architecture], RTL_OSVERSIONINFOEXW, RTL_OSVERSIONINFOEXW structure [Kernel-Mode Driver Architecture], _OSVERSIONINFOEXW, kernel.rtl_osversioninfoexw, kstruct_d_a7e48147-5619-4ab4-b83a-18139aa0a2c5.xml, wdm/PRTL_OSVERSIONINFOEXW, wdm/RTL_OSVERSIONINFOEXW"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	RTL_OSVERSIONINFOEXW
product:
- Windows
targetos: Windows
req.typenames: OSVERSIONINFOEXW, *POSVERSIONINFOEXW, *LPOSVERSIONINFOEXW, RTL_OSVERSIONINFOEXW, *PRTL_OSVERSIONINFOEXW
req.product: Windows 10 or later.
---

# _OSVERSIONINFOEXW structure


## -description


The <b>RTL_OSVERSIONINFOEXW</b> structure contains operating system version information.


## -struct-fields




### -field dwOSVersionInfoSize

The size, in bytes, of an <b>RTL_OSVERSIONINFOEXW</b> structure. This member must be set before the structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff561910">RtlGetVersion</a>.


### -field dwMajorVersion

The major version number of the operating system. For example, for Windows 2000, the major version number is five. For more information, see the table in Remarks.


### -field dwMinorVersion

The minor version number of the operating system. For example, for Windows 2000, the minor version number is zero. For more information, see the table in Remarks.


### -field dwBuildNumber

The build number of the operating system.


### -field dwPlatformId

The operating system platform. For Win32 on NT-based operating systems, <b>RtlGetVersion</b> returns the value VER_PLATFORM_WIN32_NT.


### -field szCSDVersion

The service-pack version string. This member contains a null-terminated string, such as "Service Pack 3", which indicates the latest service pack installed on the system. If no service pack is installed, <b>RtlGetVersion</b> might not initialize this string. Initialize <i>szCSDVersion</i> to zero (empty string) before the call to <b>RtlGetVersion</b>.


### -field wServicePackMajor

The major version number of the latest service pack installed on the system. For example, for Service Pack 3, the major version number is three. If no service pack has been installed, the value is zero.


### -field wServicePackMinor

The minor version number of the latest service pack installed on the system. For example, for Service Pack 3, the minor version number is zero.


### -field wSuiteMask

The product suites available on the system. This member is set to zero or to the bitwise OR of one or more of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_SUITE_BACKOFFICE

</td>
<td>
Microsoft BackOffice components are installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_BLADE

</td>
<td>
Windows Server 2003, Web Edition is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_COMPUTE_SERVER

</td>
<td>
Windows Server 2003, Compute Cluster Edition is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_DATACENTER

</td>
<td>
Windows Server 2008 Datacenter, Windows Server 2003, Datacenter Edition, or Windows 2000 Datacenter Server is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_ENTERPRISE

</td>
<td>
Windows Server 2008 Enterprise, Windows Server 2003, Enterprise Edition, or Windows 2000 Advanced Server is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_EMBEDDEDNT

</td>
<td>
Windows XP Embedded is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_PERSONAL

</td>
<td>
Windows Vista Home Premium, Windows Vista Home Basic, or Windows XP Home Edition is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_SINGLEUSERTS

</td>
<td>
Remote Desktop is supported, but only one interactive session is supported. This value is set unless the system is running in application server mode.

</td>
</tr>
<tr>
<td>
VER_SUITE_SMALLBUSINESS (see note)

</td>
<td>
Microsoft Small Business Server was once installed on the system, but may have been upgraded to another version of Windows. For more information about this flag bit, see the following Remarks section.

</td>
</tr>
<tr>
<td>
VER_SUITE_SMALLBUSINESS_RESTRICTED

</td>
<td>
Microsoft Small Business Server is installed with the restrictive client license in force. For more information about this flag bit, see the following Remarks section.

</td>
</tr>
<tr>
<td>
VER_SUITE_STORAGE_SERVER

</td>
<td>
Windows Storage Server 2003 R2 or Windows Storage Server 2003 is installed.

</td>
</tr>
<tr>
<td>
VER_SUITE_TERMINAL

</td>
<td>
Terminal Services is installed. This value is always set.

If VER_SUITE_TERMINAL is set but VER_SUITE_SINGLEUSERTS is not set, the operating system is running in application server mode.

</td>
</tr>
<tr>
<td>
VER_SUITE_WH_SERVER

</td>
<td>
Windows Home Server is installed.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>    You should not rely solely on the VER_SUITE_SMALLBUSINESS flag to determine whether Small Business Server is currently installed. Both this flag and the VER_SUITE_SMALLBUSINESS_RESTRICTED flag are set when this product suite is installed. If you upgrade this installation to Windows Server, Standard Edition, the VER_SUITE_SMALLBUSINESS_RESTRICTED flag is cleared, but the VER_SUITE_SMALLBUSINESS flag remains set, which, in this case, indicates that Small Business Server was previously installed on this system. If this installation is further upgraded to Windows Server, Enterprise Edition, the VER_SUITE_SMALLBUSINESS flag remains set.</div>
<div> </div>

### -field wProductType

The product type. This member contains additional information about the system. This member can be one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_NT_WORKSTATION

</td>
<td>
Windows 2000 or later professional version

</td>
</tr>
<tr>
<td>
VER_NT_DOMAIN_CONTROLLER

</td>
<td>
Windows 2000 or later domain controller

</td>
</tr>
<tr>
<td>
VER_NT_SERVER

</td>
<td>
Windows 2000 or later server

</td>
</tr>
</table>
 


### -field wReserved

Reserved for future use.


## -remarks



The information in this structure includes the major and minor version numbers, the build number, the platform identifier, the installed product suites, and the latest service pack that is installed on the system. This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561910">RtlGetVersion</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563026">RtlVerifyVersionInfo</a> routines.

Relying on version information is not always the best way to test whether a feature is available. For guidance, refer to the documentation for the feature you are interested in.

If possible, design the version detection code in your driver to enable the driver to run on future versions of Windows. If your driver requires a particular operating system version, be sure to treat this version as the minimum supported version, and not as the only version on which the driver can run.

The following table summarizes the version information that is returned by supported versions of Windows. Use the information in the "Other" column to distinguish between operating systems with identical version numbers.

<table>
<tr>
<th>Operating system</th>
<th>Version number</th>
<th>dwMajorVersion</th>
<th>dwMinorVersion</th>
<th>Other</th>
</tr>
<tr>
<td>
Windows 10

</td>
<td>
10.0

</td>
<td>
10

</td>
<td>
0

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows 8.1

</td>
<td>
6.3

</td>
<td>
6

</td>
<td>
3

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows 8

</td>
<td>
6.2

</td>
<td>
6

</td>
<td>
2

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows Server 2012

</td>
<td>
6.2

</td>
<td>
6

</td>
<td>
2

</td>
<td>
<b>wProductType</b> != VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows 7

</td>
<td>
6.1

</td>
<td>
6

</td>
<td>
1

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows Server 2008 R2

</td>
<td>
6.1

</td>
<td>
6

</td>
<td>
1

</td>
<td>
<b>wProductType</b> != VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows Server 2008

</td>
<td>
6.0

</td>
<td>
6

</td>
<td>
0

</td>
<td>
<b>wProductType</b> != VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows Vista

</td>
<td>
6.0

</td>
<td>
6

</td>
<td>
0

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION

</td>
</tr>
<tr>
<td>
Windows Home Server

</td>
<td>
5.2

</td>
<td>
5

</td>
<td>
2

</td>
<td>
<b>wSuiteMask</b> == VER_SUITE_WH_SERVER

</td>
</tr>
<tr>
<td>
Windows Server 2003

</td>
<td>
5.2

</td>
<td>
5

</td>
<td>
2

</td>
<td>
Not applicable

</td>
</tr>
<tr>
<td>
Windows XP Professional x64 Edition (see note)

</td>
<td>
5.2

</td>
<td>
5

</td>
<td>
2

</td>
<td>
<b>wProductType</b> == VER_NT_WORKSTATION 

</td>
</tr>
<tr>
<td>
Windows XP

</td>
<td>
5.1

</td>
<td>
5

</td>
<td>
1

</td>
<td>
Not applicable

</td>
</tr>
<tr>
<td>
Windows 2000

</td>
<td>
5.0

</td>
<td>
5

</td>
<td>
0

</td>
<td>
Not applicable

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  Only a 64-bit kernel-mode driver can run on Windows XP Professional x64 Edition. Therefore, a 32-bit kernel-mode driver can safely omit checking for this version of Windows.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563624">RTL_OSVERSIONINFOW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561910">RtlGetVersion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563026">RtlVerifyVersionInfo</a>
 

 

