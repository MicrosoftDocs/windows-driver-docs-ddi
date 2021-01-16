---
UID: NS:ntifs._IO_PRIORITY_INFO
title: _IO_PRIORITY_INFO (ntifs.h)
description: The IO_PRIORITY_INFO structure is used to hold thread priority information.
old-location: ifsk\io_priority_info.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IO_PRIORITY_INFO structure"]
ms.keywords: "*PIO_PRIORITY_INFO, IO_PRIORITY_INFO, IO_PRIORITY_INFO structure [Installable File System Drivers], PIO_PRIORITY_INFO, PIO_PRIORITY_INFO structure pointer [Installable File System Drivers], _IO_PRIORITY_INFO, ifsk.io_priority_info, ntifs/IO_PRIORITY_INFO, ntifs/PIO_PRIORITY_INFO, othersystemstructures_19a36a9e-6950-4a52-b1e3-e25977777952.xml"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
targetos: Windows
req.typenames: IO_PRIORITY_INFO, *PIO_PRIORITY_INFO
f1_keywords:
 - _IO_PRIORITY_INFO
 - ntifs/_IO_PRIORITY_INFO
 - PIO_PRIORITY_INFO
 - ntifs/PIO_PRIORITY_INFO
 - IO_PRIORITY_INFO
 - ntifs/IO_PRIORITY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _IO_PRIORITY_INFO
 - PIO_PRIORITY_INFO
 - IO_PRIORITY_INFO
---

# _IO_PRIORITY_INFO structure


## -description

The IO_PRIORITY_INFO structure is used to hold thread priority information.

## -struct-fields

### -field Size

Read-only member initialized by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a> routine.

### -field ThreadPriority

Read-only member used to hold a thread's priority.

### -field PagePriority

Read-only member used to hold a thread's paging priority.

### -field IoPriority

Read-only member used to hold a thread's I/O priority.

## -remarks

The IO_PRIORITY_INFO structure is used by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a> and <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a> routines to save and set a thread's priority state.

A structure of type IO_PRIORITY_INFO must be initialized before first use by calling either the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a> routine or the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a>

