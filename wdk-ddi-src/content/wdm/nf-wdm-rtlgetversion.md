---
UID: NF:wdm.RtlGetVersion
title: RtlGetVersion function (wdm.h)
description: The RtlGetVersion routine returns version information about the currently running operating system.
old-location: kernel\rtlgetversion.htm
tech.root: kernel
ms.assetid: b6e6fbc0-a35b-4086-9d7a-98dab516a816
ms.date: 04/30/2018
keywords: ["RtlGetVersion function"]
ms.keywords: RtlGetVersion, RtlGetVersion routine [Kernel-Mode Driver Architecture], k109_7e44c42c-d5c6-4727-b529-7e55b308fddd.xml, kernel.rtlgetversion, wdm/RtlGetVersion
f1_keywords:
 - "wdm/RtlGetVersion"
 - "RtlGetVersion"
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlGetVersion
targetos: Windows
req.typenames: 
---

# RtlGetVersion function


## -description


The <b>RtlGetVersion</b> routine returns version information about the currently running operating system.


## -parameters




### -param lpVersionInformation 
[out]
Pointer to either a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfow">RTL_OSVERSIONINFOW</a> structure or a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_osversioninfoexw">RTL_OSVERSIONINFOEXW</a> structure that contains the version information about the currently running operating system. A caller specifies which input structure is used by setting the <b>dwOSVersionInfoSize</b> member of the structure to the size in bytes of the structure that is used. 


## -returns



<b>RtlGetVersion</b> returns STATUS_SUCCESS.




## -remarks



<b>RtlGetVersion</b> is the kernel-mode equivalent of the user-mode <b>GetVersionEx</b> function in the Windows SDK. See the example in the Windows SDK that shows how to get the system version.

When using <b>RtlGetVersion</b> to determine whether a particular version of the operating system is running, a caller should check for version numbers that are greater than or equal to the required version number. This ensures that a version test succeeds for later versions of Windows.

Because operating system features can be added in a redistributable DLL, checking only the major and minor version numbers is not the most reliable way to verify the presence of a specific system feature. A driver should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlverifyversioninfo">RtlVerifyVersionInfo</a> to test for the presence of a specific system feature. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psgetversion">PsGetVersion</a>
 

 

