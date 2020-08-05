---
UID: NS:wdm._OSVERSIONINFOW
title: _OSVERSIONINFOW (wdm.h)
description: The RTL_OSVERSIONINFOW structure contains operating system version information.
old-location: kernel\rtl_osversioninfow.htm
tech.root: kernel
ms.assetid: 04e50a2c-eb85-4fc8-9751-798397eddf95
ms.date: 04/30/2018
keywords: ["OSVERSIONINFOW structure"]
ms.keywords: "*LPOSVERSIONINFOW, *POSVERSIONINFOW, *PRTL_OSVERSIONINFOW, OSVERSIONINFO, OSVERSIONINFOW, PRTL_OSVERSIONINFOW, PRTL_OSVERSIONINFOW structure pointer [Kernel-Mode Driver Architecture], RTL_OSVERSIONINFOW, RTL_OSVERSIONINFOW structure [Kernel-Mode Driver Architecture], _OSVERSIONINFOW, kernel.rtl_osversioninfow, kstruct_d_61d86312-0550-4bce-81c8-bb29551cc586.xml, wdm/PRTL_OSVERSIONINFOW, wdm/RTL_OSVERSIONINFOW"
f1_keywords:
 - "wdm/RTL_OSVERSIONINFOW"
 - "RTL_OSVERSIONINFOW"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- RTL_OSVERSIONINFOW
targetos: Windows
req.typenames: OSVERSIONINFOW, *POSVERSIONINFOW, *LPOSVERSIONINFOW, RTL_OSVERSIONINFOW, *PRTL_OSVERSIONINFOW
---

# _OSVERSIONINFOW structure


## -description


The <b>RTL_OSVERSIONINFOW</b> structure contains operating system version information. The information includes major and minor version numbers, a build number, a platform identifier, and descriptive text about the operating system. The <b>RTL_OSVERSIONINFOW</b> structure is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a>. 


## -struct-fields




### -field dwOSVersionInfoSize

The size in bytes of an <b>RTL_OSVERSIONINFOW</b> structure. This member must be set before the structure is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a>.


### -field dwMajorVersion

The major version number of the operating system. For example, for Windows 2000, the major version number is five. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a>.


### -field dwMinorVersion

The minor version number of the operating system. For example, for Windows 2000 the minor version number is zero. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a>. 


### -field dwBuildNumber

The build number of the operating system.


### -field dwPlatformId

The operating system platform. For Microsoft Win32 on NT-based operating systems, <b>RtlGetVersion</b> returns the value VER_PLATFORM_WIN32_NT.


### -field szCSDVersion

The service-pack version string. This member contains a null-terminated string, such as "Service Pack 3", which indicates the latest service pack installed on the system. If no service pack is installed, <b>RtlGetVersion</b> might not initialize this string. Initialize <i>szCSDVersion</i> to zero (empty string) before the call to <b>RtlGetVersion</b>.


## -remarks



For a list of the major and minor version numbers for the various versions of Windows, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlverifyversioninfo">RtlVerifyVersionInfo</a>
 

 

