---
UID: NF:ntddk.KeQueryActiveGroupCount
title: KeQueryActiveGroupCount function
author: windows-driver-content
description: The KeQueryActiveGroupCount routine returns the number of active processor groups in a multiprocessor system.
old-location: kernel\kequeryactivegroupcount.htm
old-project: kernel
ms.assetid: a5447dd8-6a4f-4686-b4e3-7deb4b61ff92
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_29b5c7ca-1596-4a3e-8cda-20c6ccec4ebb.xml, KeQueryActiveGroupCount routine [Kernel-Mode Driver Architecture], kernel.kequeryactivegroupcount, KeQueryActiveGroupCount, wdm/KeQueryActiveGroupCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
-	KeQueryActiveGroupCount
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# KeQueryActiveGroupCount function


## -description


The <b>KeQueryActiveGroupCount</b> routine returns the number of active processor groups in a multiprocessor system.


## -syntax


````
USHORT KeQueryActiveGroupCount(void);
````


## -parameters






## -returns



<b>KeQueryActiveGroupCount</b> returns a count of the active groups.




## -remarks



A processor group is active if it contains one or more active logical processors.

An active logical processor is a logical processor that Windows has started up and added to a multiprocessor system. The term <i>active processor</i> applies to a processor that is available to perform processing work, regardless of whether the processor is currently performing processing work or is idle. In some systems, the number of active processors might remain unchanged from system startup to shutdown. In other systems, Windows might dynamically add active processors while the system is running. Windows never removes active processors from a system.

Thus, the number of active processors in a multiprocessor system can increase between system startup and shutdown, but this number never decreases. Similarly, the number of active groups in the system can increase if a processor is dynamically added to an inactive group while the system is running. The number of active groups never decreases.

In contrast, the value that is returned by <a href="..\wdm\nf-wdm-kequerymaximumgroupcount.md">KeQueryMaximumGroupCount</a> remains constant during runtime. This value is the maximum number of groups that the system can have.

Call the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a> routine to determine the number of active logical processors in a particular group.

Windows 7 is the first version of Windows to support processor groups. In Windows 7, only 64-bit versions of Windows support multiple groups; 32-bit versions of Windows support only one group. If a multiprocessor system is running a 64-bit version of Windows and contains no more than 64 logical processors, Windows assigns all processors to group 0. A multiprocessor system that is running a 32-bit version of Windows can contain no more than 32 processors.




## -see-also

<a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a>



<a href="..\wdm\nf-wdm-kequerymaximumgroupcount.md">KeQueryMaximumGroupCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryActiveGroupCount routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

