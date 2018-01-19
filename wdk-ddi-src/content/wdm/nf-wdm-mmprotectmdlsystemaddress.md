---
UID: NF:wdm.MmProtectMdlSystemAddress
title: MmProtectMdlSystemAddress function
author: windows-driver-content
description: The MmProtectMdlSystemAddress routine sets the protection type for a memory address range.
old-location: kernel\mmprotectmdlsystemaddress.htm
old-project: kernel
ms.assetid: e0ccc6e8-9351-4440-808b-e0b8eef48bc2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmProtectMdlSystemAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmProtectMdlSystemAddress
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmProtectMdlSystemAddress function



## -description
The <b>MmProtectMdlSystemAddress</b> routine sets the protection type for a memory address range.



## -syntax

````
NTSTATUS MmProtectMdlSystemAddress(
  _In_ PMDLX MemoryDescriptorList,
  _In_ ULONG NewProtect
);
````


## -parameters

### -param MemoryDescriptorList [in]

Specifies the memory address range to set the protection type for. 


### -param NewProtect [in]

Specifies the new protection setting for the memory pages. Drivers should specify one of the following values:




### -param PAGE_NOACCESS

The underlying memory pages cannot be read or written. 


### -param PAGE_READONLY

The underlying memory pages can only be read, not written. 


### -param PAGE_READWRITE

The underlying memory pages can be read or written. 


### -param PAGE_EXECUTE

The underlying memory pages can be executed, but not read or written.


### -param PAGE_EXECUTE_READ

The underlying memory pages can be executed or read, but not written.


### -param PAGE_EXECUTE_READWRITE

The underlying memory pages can be executed, read, or written.

</dd>
</dl>

## -returns
<b>MmProtectMdlSystemAddress</b> returns an NTSTATUS code. The possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine successfully changed the protection type for the memory address range.
<dl>
<dt><b>STATUS_INVALID_PAGE_PROTECTION</b></dt>
</dl>The value specified for <i>NewProtect</i> is not a valid one for this routine.
<dl>
<dt><b>STATUS_NOT_MAPPED_VIEW</b></dt>
</dl>The MDL has not yet been mapped. <b>MmProtectMdlSystemAddress</b> can only be used on MDLs that have already been mapped.

 


## -remarks
The <b>MmProtectMdlSystemAddress</b> routine can only be called on an MDL that has already been mapped. For example, the routine can be called on an MDL mapped by <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmProtectMdlSystemAddress routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

