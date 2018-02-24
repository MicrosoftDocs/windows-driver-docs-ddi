---
UID: NF:ntddk.KeQueryMaximumGroupCount
title: KeQueryMaximumGroupCount function
author: windows-driver-content
description: The KeQueryMaximumGroupCount routine returns the maximum number of groups in a multiprocessor system.
old-location: kernel\kequerymaximumgroupcount.htm
old-project: kernel
ms.assetid: b5cf231b-1a78-485f-bf26-fe50fbe63d08
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeQueryMaximumGroupCount, KeQueryMaximumGroupCount routine [Kernel-Mode Driver Architecture], kernel.kequerymaximumgroupcount, k105_c1e0cc3e-f9d0-4570-8a56-b799d2ca5d14.xml, wdm/KeQueryMaximumGroupCount
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
-	KeQueryMaximumGroupCount
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# KeQueryMaximumGroupCount function


## -description


The <b>KeQueryMaximumGroupCount</b> routine returns the maximum number of groups in a multiprocessor system.


## -syntax


````
USHORT KeQueryMaximumGroupCount(void);
````


## -parameters






## -returns



<b>KeQueryMaximumGroupCount</b> returns the maximum number of groups. 




## -remarks



The value that is returned by <b>KeQueryMaximumGroupCount</b> remains constant during runtime. This value depends on the hardware configuration of the multiprocessor system, but it can never exceed a fixed limit that is set by the Windows operating system.

In Windows 7, the maximum number of groups in a multiprocessor system is four, but this value might change in future versions of Windows. The safest way to determine the maximum number of groups in Windows 7 or a later versions of the Windows operating system is to call <b>KeQueryMaximumGroupCount</b>. Kernel-mode drivers that call <b>KeQueryMaximumGroupCount</b> will not require code changes if the formula that is used to calculate the maximum number of groups changes in a future version of Windows.

To obtain the number of active groups in a multiprocessor system, call the <a href="..\ntddk\nf-ntddk-kequeryactivegroupcount.md">KeQueryActiveGroupCount</a> routine.




## -see-also

<a href="..\ntddk\nf-ntddk-kequeryactivegroupcount.md">KeQueryActiveGroupCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryMaximumGroupCount routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

