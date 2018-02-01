---
UID: NF:wdm.ZwUnmapViewOfSection
title: ZwUnmapViewOfSection function
author: windows-driver-content
description: The ZwUnmapViewOfSection routine unmaps a view of a section from the virtual address space of a subject process.
old-location: kernel\zwunmapviewofsection.htm
old-project: kernel
ms.assetid: ebc67162-4e36-4af8-bc3b-764633dcda5d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwUnmapViewOfSection, k111_4353325c-d2a1-47b3-b58a-b62929c417f9.xml, ZwUnmapViewOfSection routine [Kernel-Mode Driver Architecture], wdm/ZwUnmapViewOfSection, wdm/NtUnmapViewOfSection, kernel.zwunmapviewofsection, NtUnmapViewOfSection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwUnmapViewOfSection
-	NtUnmapViewOfSection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwUnmapViewOfSection function


## -description


The <b>ZwUnmapViewOfSection</b> routine unmaps a <a href="https://msdn.microsoft.com/library/windows/hardware/dn927297">view</a> of a section from the virtual address space of a subject process.


## -syntax


````
NTSTATUS ZwUnmapViewOfSection(
  _In_     HANDLE ProcessHandle,
  _In_opt_ PVOID  BaseAddress
);
````


## -parameters




### -param ProcessHandle [in]

Handle to a process object that was previously passed to <a href="..\wdm\nf-wdm-zwmapviewofsection.md">ZwMapViewOfSection</a>.


### -param BaseAddress [in, optional]

Pointer to the base virtual address of the view to unmap. This value can be any virtual address within the view.


## -returns


<b>ZwUnmapViewOfSection</b> returns an NTSTATUS value. Possible return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully performed the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have access rights to the process object or to the base virtual address of the view.

</td>
</tr>
</table> 



## -remarks


This routine unmaps the entire view of the section that contains <i>BaseAddress</i> from the virtual address space of the specified process—even if <i>BaseAddress</i> does not point to the beginning of the view.

On return from <b>ZwUnmapViewOfSection</b>, the virtual-address region occupied by the view is no longer reserved and is available to map other views or private pages. If the view was also the last reference to the underlying section, all committed pages in the section are decommitted, and the section is deleted.
<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557711">NtUnmapViewOfSection</a>" instead of "<b>ZwUnmapViewOfSection</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-zwopensection.md">ZwOpenSection</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wdm\nf-wdm-zwmapviewofsection.md">ZwMapViewOfSection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwUnmapViewOfSection routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

