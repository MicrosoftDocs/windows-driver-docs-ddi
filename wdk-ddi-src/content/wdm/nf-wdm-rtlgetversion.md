---
UID: NF:wdm.RtlGetVersion
title: RtlGetVersion function
author: windows-driver-content
description: The RtlGetVersion routine returns version information about the currently running operating system.
old-location: kernel\rtlgetversion.htm
old-project: kernel
ms.assetid: b6e6fbc0-a35b-4086-9d7a-98dab516a816
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlGetVersion routine [Kernel-Mode Driver Architecture], kernel.rtlgetversion, wdm/RtlGetVersion, RtlGetVersion, k109_7e44c42c-d5c6-4727-b529-7e55b308fddd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlGetVersion
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlGetVersion function


## -description


The <b>RtlGetVersion</b> routine returns version information about the currently running operating system.


## -syntax


````
NTSTATUS RtlGetVersion(
  _Out_ PRTL_OSVERSIONINFOW lpVersionInformation
);
````


## -parameters




### -param lpVersionInformation [out]

Pointer to either a <a href="..\wdm\ns-wdm-_osversioninfow.md">RTL_OSVERSIONINFOW</a> structure or a <a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a> structure that contains the version information about the currently running operating system. A caller specifies which input structure is used by setting the <b>dwOSVersionInfoSize</b> member of the structure to the size in bytes of the structure that is used. 


## -returns


<b>RtlGetVersion</b> returns STATUS_SUCCESS.



## -remarks


<b>RtlGetVersion</b> is the kernel-mode equivalent of the user-mode <b>GetVersionEx</b> function in the Windows SDK. See the example in the Windows SDK that shows how to get the system version.

When using <b>RtlGetVersion</b> to determine whether a particular version of the operating system is running, a caller should check for version numbers that are greater than or equal to the required version number. This ensures that a version test succeeds for later versions of Windows.

Because operating system features can be added in a redistributable DLL, checking only the major and minor version numbers is not the most reliable way to verify the presence of a specific system feature. A driver should use <a href="..\wdm\nf-wdm-rtlverifyversioninfo.md">RtlVerifyVersionInfo</a> to test for the presence of a specific system feature. 



## -see-also

<a href="..\wdm\nf-wdm-psgetversion.md">PsGetVersion</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlGetVersion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

