---
UID: NS:ntifs._IO_PRIORITY_INFO
title: _IO_PRIORITY_INFO
author: windows-driver-content
description: The IO_PRIORITY_INFO structure is used to hold thread priority information.
old-location: ifsk\io_priority_info.htm
old-project: ifsk
ms.assetid: 1161b239-3ad1-4a0c-9d11-4a3a88d361b3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _IO_PRIORITY_INFO, *PIO_PRIORITY_INFO, IO_PRIORITY_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_PRIORITY_INFO
req.alt-loc: ntifs.h
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
req.typenames: *PIO_PRIORITY_INFO, IO_PRIORITY_INFO
---

# _IO_PRIORITY_INFO structure



## -description
The IO_PRIORITY_INFO structure is used to hold thread priority information.



## -syntax

````
typedef struct _IO_PRIORITY_INFO {
  ULONG            Size;
  ULONG            ThreadPriority;
  ULONG            PagePriority;
  IO_PRIORITY_HINT IoPriority;
} IO_PRIORITY_INFO, *PIO_PRIORITY_INFO;
````


## -struct-fields

### -field Size

Read-only member initialized by the <a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a> routine.


### -field ThreadPriority

Read-only member used to hold a thread's priority.


### -field PagePriority

Read-only member used to hold a thread's paging priority.


### -field IoPriority

Read-only member used to hold a thread's I/O priority.


## -remarks
The IO_PRIORITY_INFO structure is used by the <a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a> and <a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a> routines to save and set a thread's priority state.

A structure of type IO_PRIORITY_INFO must be initialized before first use by calling either the <a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a> routine or the <a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a> routine.


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IO_PRIORITY_INFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

