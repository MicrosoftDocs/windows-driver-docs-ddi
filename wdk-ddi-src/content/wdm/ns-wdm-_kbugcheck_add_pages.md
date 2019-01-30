---
UID: NS:wdm._KBUGCHECK_ADD_PAGES
title: "_KBUGCHECK_ADD_PAGES" (wdm.h)
description: The KBUGCHECK_ADD_PAGES structure describes one or more pages of driver-supplied data to be written by a BugCheckAddPagesCallback callback routine to the crash dump file.
old-location: kernel\kbugcheck_add_pages.htm
tech.root: kernel
ms.assetid: 91d5b91b-6151-4da7-b0a8-74a2e99474b5
ms.date: 04/30/2018
ms.keywords: "*PKBUGCHECK_ADD_PAGES, KBUGCHECK_ADD_PAGES, KBUGCHECK_ADD_PAGES structure [Kernel-Mode Driver Architecture], PKBUGCHECK_ADD_PAGES, PKBUGCHECK_ADD_PAGES structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_ADD_PAGES, kernel.kbugcheck_add_pages, kstruct_c_4d14d1f9-fada-4eaa-afc7-88228745fcc1.xml, wdm/KBUGCHECK_ADD_PAGES, wdm/PKBUGCHECK_ADD_PAGES"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008 and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	KBUGCHECK_ADD_PAGES
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_ADD_PAGES, *PKBUGCHECK_ADD_PAGES
---

# _KBUGCHECK_ADD_PAGES structure


## -description


The <b>KBUGCHECK_ADD_PAGES</b> structure describes one or more pages of driver-supplied data to be written by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a> callback routine to the crash dump file. 


## -struct-fields




### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, <b>Context</b> is <b>NULL</b>.


### -field Flags


      Contains flags that describe the add-page request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits: 
      





#### KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS

Indicates that the <b>Address</b> member contains a virtual address.



#### KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS

Indicates that the <b>Address</b> member contains a physical address.



#### KB_ADD_PAGES_FLAG_ADDITIONAL_RANGES_EXIST

Indicates that the callback routine requests that it be called again so that it can add more pages.

The callback routine must set either the KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS flag or the KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS flag, but not both. On entry to the callback routine, <b>Flags</b> is initialized to zero.


### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h    header file.


### -field Address

Specifies the physical or virtual address of the page or pages that the callback routine requests be added to the crash dump file.


### -field Count

Specifies the number of contiguous pages to add to the crash dump file, starting from the virtual or physical address that is specified by the <b>Address</b> member. If <b>Count</b> &gt; 1 and <b>Address</b> is a virtual address, the pages are contiguous in virtual memory space. If <b>Count</b> &gt; 1 and <b>Address</b> is a physical address, the pages are contiguous in physical memory space. The callback routine can set this member to zero to indicate that it does not need to add any pages to the crash dump file.


## -remarks



In a call to the <i>BugCheckAddPagesCallback</i> callback routine, the operating system sets the <i>Reason</i> parameter to <b>KbCallbackAddPages</b>, and sets the <i>ReasonSpecificData</i> parameter to point to a <b>KBUGCHECK_ADD_PAGES</b> structure.

For more information about how this structure is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a>
 

 

