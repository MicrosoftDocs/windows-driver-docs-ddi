---
UID: NF:wdm.ZwQuerySymbolicLinkObject
title: ZwQuerySymbolicLinkObject function
author: windows-driver-content
description: The ZwQuerySymbolicLinkObject routine returns a Unicode string that contains the target of a symbolic link.
old-location: kernel\zwquerysymboliclinkobject.htm
tech.root: kernel
ms.assetid: 0294c840-2912-4137-886f-832e9f21bbea
ms.date: 4/30/2018
ms.keywords: NtQuerySymbolicLinkObject, ZwQuerySymbolicLinkObject, ZwQuerySymbolicLinkObject routine [Kernel-Mode Driver Architecture], k111_0909b6b6-fa4d-421f-b17f-8201a254990b.xml, kernel.zwquerysymboliclinkobject, wdm/NtQuerySymbolicLinkObject, wdm/ZwQuerySymbolicLinkObject
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwQuerySymbolicLinkObject
-	NtQuerySymbolicLinkObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQuerySymbolicLinkObject function


## -description


The <b>ZwQuerySymbolicLinkObject</b> routine returns a Unicode string that contains the target of a symbolic link.


## -parameters




### -param LinkHandle [in]

Handle to the symbolic-link object that you want to query. This handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567030">ZwOpenSymbolicLinkObject</a>. 


### -param LinkTarget [in, out]

Pointer to an initialized Unicode string that receives the target of the symbolic link.


### -param ReturnedLength [out, optional]

 contains the maximum number of bytes to copy into the Unicode string at <i>LinkTarget</i>. On output, the unsigned long integer contains the length of the Unicode string naming the target of the symbolic link. 


## -returns



<b>ZwQuerySymbolicLinkObject</b> returns either STATUS_SUCCESS to indicate the routine completed without error or STATUS_BUFFER_TOO_SMALL if the Unicode string provided at <i>LinkTarget</i> is too small to hold the returned string.




## -remarks



Before calling this routine, driver writers must ensure that the Unicode string at <i>LinkTarget </i>has been properly initialized and a buffer for the string has been allocated. The <b>MaximumLength</b> and <b>Buffer</b> members of the Unicode string must be set before calling <b>ZwQuerySymbolicLinkObject</b> or the call will fail.

If <b>ZwQuerySymbolicLinkObject</b> returns STATUS_BUFFER_TOO_SMALL drivers should examine the value returned at <i>ReturnedLength</i>. The number returned in this variable indicates the maximum length that the Unicode string for the target of the symbolic link.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtQuerySymbolicLinkObject</b>" instead of "<b>ZwQuerySymbolicLinkObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567030">ZwOpenSymbolicLinkObject</a>
 

 

