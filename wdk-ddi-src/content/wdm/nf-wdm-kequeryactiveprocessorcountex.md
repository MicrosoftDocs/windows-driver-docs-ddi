---
UID: NF:wdm.KeQueryActiveProcessorCountEx
title: KeQueryActiveProcessorCountEx function
author: windows-driver-content
description: The KeQueryActiveProcessorCountEx routine returns the number of active logical processors in a specified group in a multiprocessor system or in the entire system.
old-location: kernel\kequeryactiveprocessorcountex.htm
old-project: kernel
ms.assetid: 3884eb16-56a0-4b48-abf3-a74794b2c996
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KeQueryActiveProcessorCountEx, k105_7cd9a091-c100-4b0c-9ea0-9b831407d5a1.xml, KeQueryActiveProcessorCountEx, kernel.kequeryactiveprocessorcountex, KeQueryActiveProcessorCountEx routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
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
req.irql: Any level
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	KeQueryActiveProcessorCountEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryActiveProcessorCountEx function


## -description


The <b>KeQueryActiveProcessorCountEx</b> routine returns the number of active logical processors in a specified group in a multiprocessor system or in the entire system. 


## -syntax


````
ULONG KeQueryActiveProcessorCountEx(
  _In_ USHORT GroupNumber
);
````


## -parameters




### -param GroupNumber [in]

The group number. If a multiprocessor system contains <i>n</i> groups, valid group numbers range from 0 to <i>n</i>-1. To count all active processors in all groups in the system, set this parameter to ALL_PROCESSOR_GROUPS, which is defined in header files Winnt.h and Ntdef.h. 


## -returns


<b>KeQueryActiveProcessorCountEx</b> returns the number of active logical processors in the group. If <i>GroupNumber</i> is not a valid group number and is not ALL_PROCESSOR_GROUPS, it returns zero. 



## -remarks


An active logical processor is a logical processor that Windows has started up and added to a multiprocessor system. The term active processor applies to a processor that is available to perform processing work, regardless of whether the processor is currently performing processing work or is idle. In some systems, the number of active processors might remain unchanged from system startup to shutdown. In other systems, Windows might dynamically add active processors while the system is running. Windows never removes active processors from a system. Thus, the number of active processors in a multiprocessor system can increase between system startup and shutdown, but this number never decreases.

A related routine, <a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>, returns an active processor count, but this routine, unlike <b>KeQueryActiveProcessorCountEx</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeQueryActiveProcessorCount</b> returns the active processor count in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeQueryActiveProcessorCount</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeQueryActiveProcessorCountEx</b> instead of <b>KeQueryActiveProcessorCount</b>.

For a code example that uses <b>KeQueryActiveProcessorCountEx</b>, see <a href="..\wdm\nf-wdm-kegetprocessornumberfromindex.md">KeGetProcessorNumberFromIndex</a>. 



## -see-also

<a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>

<a href="..\wdm\nf-wdm-kegetprocessornumberfromindex.md">KeGetProcessorNumberFromIndex</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryActiveProcessorCountEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

