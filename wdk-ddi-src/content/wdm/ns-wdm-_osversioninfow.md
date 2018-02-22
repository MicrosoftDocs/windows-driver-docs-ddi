---
UID: NS:wdm._OSVERSIONINFOW
title: "_OSVERSIONINFOW"
author: windows-driver-content
description: The RTL_OSVERSIONINFOW structure contains operating system version information.
old-location: kernel\rtl_osversioninfow.htm
old-project: kernel
ms.assetid: 04e50a2c-eb85-4fc8-9751-798397eddf95
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PRTL_OSVERSIONINFOW structure pointer [Kernel-Mode Driver Architecture], *LPOSVERSIONINFOW, RTL_OSVERSIONINFOW, *POSVERSIONINFOW, _OSVERSIONINFOW, kernel.rtl_osversioninfow, wdm/PRTL_OSVERSIONINFOW, RTL_OSVERSIONINFOW structure [Kernel-Mode Driver Architecture], PRTL_OSVERSIONINFOW, kstruct_d_61d86312-0550-4bce-81c8-bb29551cc586.xml, wdm/RTL_OSVERSIONINFOW, OSVERSIONINFOW, *PRTL_OSVERSIONINFOW, OSVERSIONINFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	RTL_OSVERSIONINFOW
product: Windows
targetos: Windows
req.typenames: "*PRTL_OSVERSIONINFOW, OSVERSIONINFOW, *POSVERSIONINFOW, RTL_OSVERSIONINFOW, *LPOSVERSIONINFOW"
req.product: Windows 10 or later.
---

# _OSVERSIONINFOW structure


## -description


The <b>RTL_OSVERSIONINFOW</b> structure contains operating system version information. The information includes major and minor version numbers, a build number, a platform identifier, and descriptive text about the operating system. The <b>RTL_OSVERSIONINFOW</b> structure is used with <a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>. 


## -syntax


````
typedef struct _OSVERSIONINFOW {
  ULONG dwOSVersionInfoSize;
  ULONG dwMajorVersion;
  ULONG dwMinorVersion;
  ULONG dwBuildNumber;
  ULONG dwPlatformId;
  WCHAR szCSDVersion[128];
} RTL_OSVERSIONINFOW, *PRTL_OSVERSIONINFOW;
````


## -struct-fields




### -field dwOSVersionInfoSize

The size in bytes of an <b>RTL_OSVERSIONINFOW</b> structure. This member must be set before the structure is used with <a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>.


### -field dwMajorVersion

The major version number of the operating system. For example, for Windows 2000, the major version number is five. For more information, see <a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a>.


### -field dwMinorVersion

The minor version number of the operating system. For example, for Windows 2000 the minor version number is zero. For more information, see <a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a>. 


### -field dwBuildNumber

The build number of the operating system.


### -field dwPlatformId

The operating system platform. For Microsoft Win32 on NT-based operating systems, <b>RtlGetVersion</b> returns the value VER_PLATFORM_WIN32_NT.


### -field szCSDVersion

The service-pack version string. This member contains a null-terminated string, such as "Service Pack 3", which indicates the latest service pack installed on the system. If no service pack is installed, <b>RtlGetVersion</b> might not initialize this string. Initialize <i>szCSDVersion</i> to zero (empty string) before the call to <b>RtlGetVersion</b>.


## -remarks



For a list of the major and minor version numbers for the various versions of Windows, see <a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a>.




## -see-also

<a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a>



<a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>



<a href="..\wdm\nf-wdm-rtlverifyversioninfo.md">RtlVerifyVersionInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RTL_OSVERSIONINFOW structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

