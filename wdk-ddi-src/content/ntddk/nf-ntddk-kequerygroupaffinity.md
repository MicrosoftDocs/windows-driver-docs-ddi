---
UID: NF:ntddk.KeQueryGroupAffinity
title: KeQueryGroupAffinity function
author: windows-driver-content
description: The KeQueryGroupAffinity routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system.
old-location: kernel\kequerygroupaffinity.htm
old-project: kernel
ms.assetid: 235ec93e-5b3c-4a19-876f-f668271a56a5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeQueryGroupAffinity, kernel.kequerygroupaffinity, wdm/KeQueryGroupAffinity, k105_9116eade-e2ed-47f4-a204-c21d456371b0.xml, KeQueryGroupAffinity routine [Kernel-Mode Driver Architecture]
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
-	KeQueryGroupAffinity
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# KeQueryGroupAffinity function


## -description


The <b>KeQueryGroupAffinity</b> routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system.


## -syntax


````
KAFFINITY KeQueryGroupAffinity(
  _In_ USHORT GroupNumber
);
````


## -parameters




### -param GroupNumber [in]

The group number. If a multiprocessor system contains <i>n</i> groups, the groups are numbered from 0 to <i>n</i>-1. To obtain the number of active groups in the system, call the <a href="..\wdm\nf-wdm-kequeryactivegroupcount.md">KeQueryActiveGroupCount</a> routine. 


## -returns



<b>KeQueryGroupAffinity</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value that identifies the active logical processors in the specified group. If the <i>GroupNumber</i> parameter value is not a valid group number, the routine returns zero. 




## -remarks



A related routine, <a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>, returns an affinity mask that represents a set of active processors, but this routine, unlike <b>KeQueryGroupAffinity</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeQueryActiveProcessors</b> returns an affinity mask for the active processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeQueryActiveProcessors</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeQueryGroupAffinity</b> instead of <b>KeQueryActiveProcessors</b>. 




## -see-also

<a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryGroupAffinity routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

