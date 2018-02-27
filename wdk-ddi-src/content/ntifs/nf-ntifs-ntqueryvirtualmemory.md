---
UID: NF:ntifs.NtQueryVirtualMemory
title: NtQueryVirtualMemory function
author: windows-driver-content
description: The ZwQueryVirtualMemory routine determines the state, protection, and type of a region of pages within the virtual address space of the subject process.
old-location: kernel\zwqueryvirtualmemory.htm
old-project: kernel
ms.assetid: 011BE902-5ED3-4AD8-B825-6850A72C1D5F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtQueryVirtualMemory, ZwQueryVirtualMemory, ZwQueryVirtualMemory routine [Kernel-Mode Driver Architecture], kernel.zwqueryvirtualmemory, ntifs/NtQueryVirtualMemory, ntifs/ZwQueryVirtualMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwQueryVirtualMemory
-	NtQueryVirtualMemory
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# NtQueryVirtualMemory function


## -description


The <b>ZwQueryVirtualMemory</b> routine determines the state,
    protection, and type of a region of pages within the virtual address
    space of the subject process.


## -syntax


````
NTSTATUS ZwQueryVirtualMemory(
  _In_      HANDLE                   ProcessHandle,
  _In_opt_  PVOID                    BaseAddress,
  _In_      MEMORY_INFORMATION_CLASS MemoryInformationClass,
  _Out_     PVOID                    MemoryInformation,
  _In_      SIZE_T                   MemoryInformationLength,
  _Out_opt_ PSIZE_T                  ReturnLength
);
````


## -parameters




### -param ProcessHandle [in]

A handle for the process in whose context the pages to be queried reside. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566431">ZwCurrentProcess</a> macro to specify the current process.




### -param BaseAddress [in, optional]

The base address of the region of pages to be
                  queried. This value is rounded down to the next host-page-
                  address boundary.


### -param MemoryInformationClass [in]

The memory information class about which
                             to retrieve information. Currently, the only supported <a href="..\ntifs\ne-ntifs-_memory_information_class.md">MEMORY_INFORMATION_CLASS</a> value is <b>MemoryBasicInformation</b>.


### -param MemoryInformation [out]

A pointer to a buffer that receives the specified
                        information.  The format and content of the buffer
                        depend on the specified information class specified in the <i>MemoryInformationClass</i> parameter. When the value <b>MemoryBasicInformation</b> is passed to <i>MemoryInformationClass</i>, the <i>MemoryInformationClass</i> parameter value is a <a href="..\ntifs\ns-ntifs-_memory_basic_information.md">MEMORY_BASIC_INFORMATION</a>. 


### -param MemoryInformationLength [in]

Specifies the length in bytes of
                              the memory information buffer.


### -param ReturnLength [out, optional]

An optional pointer which, if specified, receives the
                   number of bytes placed in the memory information buffer.


## -returns



Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified base address is outside the range of accessible addresses.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller had insufficient access rights to perform the requested action.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>MemoryInformation</i> buffer is larger than <i>MemoryInformationLength.</i>

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
A value other than <b>MemoryBasicInformation</b> was passed to the <i>MemoryInformationClass</i>  parameter.

</td>
</tr>
</table>
 




## -remarks



<b>ZwQueryVirtualMemory</b> determines the state of the first page within the region and then
    scans subsequent entries in the process address map from the
    base address upward until either the entire range of pages has been
    scanned or until a page with a non-matching set of attributes is
    encountered. The region attributes, the length of the region of pages
    with matching attributes, and an appropriate status value are
    returned.

If the entire region of pages does not have a matching set of
    attributes, then the <i>ReturnLength</i> parameter value can be used to
    compute the address and length of the region of pages that was not
    scanned.


<a href="https://msdn.microsoft.com/library/windows/hardware/dn957452">NtQueryVirtualMemory</a> and <b>ZwQueryVirtualMemory</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\ns-wdm-_power_platform_information.md">POWER_PLATFORM_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryVirtualMemory routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

