---
UID: NF:ntddk.KeQueryMaximumProcessorCountEx
title: KeQueryMaximumProcessorCountEx function
author: windows-driver-content
description: The KeQueryMaximumProcessorCountEx routine returns the maximum number of logical processors in a specified group in a multiprocessor system.
old-location: kernel\kequerymaximumprocessorcountex.htm
old-project: kernel
ms.assetid: 6ccc0f8c-d7b7-4043-8580-d35345d884cc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryMaximumProcessorCountEx, k105_594dbccc-80ed-4d33-a8ed-a6df6bfdfc09.xml, wdm/KeQueryMaximumProcessorCountEx, kernel.kequerymaximumprocessorcountex, KeQueryMaximumProcessorCountEx routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
-	KeQueryMaximumProcessorCountEx
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# KeQueryMaximumProcessorCountEx function


## -description


The <b>KeQueryMaximumProcessorCountEx</b> routine returns the maximum number of logical processors in a specified group in a multiprocessor system.


## -syntax


````
ULONG KeQueryMaximumProcessorCountEx(
  _In_ USHORT GroupNumber
);
````


## -parameters




### -param GroupNumber [in]

Specifies a group number. If a multiprocessor system contains <i>n</i> groups, the groups are numbered from 0 to <i>n</i>-1. To obtain the maximum number of processors in the system, set this parameter to ALL_PROCESSOR_GROUPS, which is defined in the Winnt.h and Ntdef.h header files.


## -returns



<b>KeQueryMaximumProcessorCountEx</b> returns the maximum number of logical processors in the specified group or in the system, as indicated by the value of the <i>GroupNumber</i> parameter.




## -remarks



The value that is returned by <b>KeQueryMaximumProcessorCountEx</b> remains constant during runtime. This value depends on the hardware configuration of the multiprocessor system, but it can never exceed a fixed limit that is set by the Windows operating system. This limit is 32 logical processors for 32-bit versions of Windows and 64 logical processors for 64-bit versions of Windows.

In contrast, the value that is returned by the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a> routine can change during runtime as processors are dynamically added to the system.

A related routine, <a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">KeQueryMaximumProcessorCount</a>, returns a maximum processor count, but this routine, unlike <b>KeQueryMaximumProcessorCountEx</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeQueryMaximumProcessorCount</b> returns the maximum number of logical processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeQueryMaximumProcessorCount</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeQueryMaximumProcessorCountEx</b> instead of <b>KeQueryMaximumProcessorCount</b>. 




## -see-also

<a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a>



<a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">KeQueryMaximumProcessorCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryMaximumProcessorCountEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

