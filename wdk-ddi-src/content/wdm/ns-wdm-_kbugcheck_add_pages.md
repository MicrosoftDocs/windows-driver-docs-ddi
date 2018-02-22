---
UID: NS:wdm._KBUGCHECK_ADD_PAGES
title: "_KBUGCHECK_ADD_PAGES"
author: windows-driver-content
description: The KBUGCHECK_ADD_PAGES structure describes one or more pages of driver-supplied data to be written by a BugCheckAddPagesCallback callback routine to the crash dump file.
old-location: kernel\kbugcheck_add_pages.htm
old-project: kernel
ms.assetid: 91d5b91b-6151-4da7-b0a8-74a2e99474b5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PKBUGCHECK_ADD_PAGES, PKBUGCHECK_ADD_PAGES, KBUGCHECK_ADD_PAGES, wdm/PKBUGCHECK_ADD_PAGES, KBUGCHECK_ADD_PAGES structure [Kernel-Mode Driver Architecture], kstruct_c_4d14d1f9-fada-4eaa-afc7-88228745fcc1.xml, wdm/KBUGCHECK_ADD_PAGES, _KBUGCHECK_ADD_PAGES, PKBUGCHECK_ADD_PAGES structure pointer [Kernel-Mode Driver Architecture], kernel.kbugcheck_add_pages"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KBUGCHECK_ADD_PAGES
product: Windows
targetos: Windows
req.typenames: "*PKBUGCHECK_ADD_PAGES, KBUGCHECK_ADD_PAGES"
req.product: Windows 10 or later.
---

# _KBUGCHECK_ADD_PAGES structure


## -description


The <b>KBUGCHECK_ADD_PAGES</b> structure describes one or more pages of driver-supplied data to be written by a <a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a> callback routine to the crash dump file. 


## -syntax


````
typedef struct _KBUGCHECK_ADD_PAGES {
  PVOID     Context;
  ULONG     Flags;
  ULONG     BugCheckCode;
  ULONG_PTR Address;
  ULONG_PTR Count;
} KBUGCHECK_ADD_PAGES, *PKBUGCHECK_ADD_PAGES;
````


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

For more information about how this structure is used, see <a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>.




## -see-also

<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_ADD_PAGES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

