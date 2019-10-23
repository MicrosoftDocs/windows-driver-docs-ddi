---
UID: NS:ntifs._IO_PRIORITY_INFO
title: _IO_PRIORITY_INFO (ntifs.h)
description: The IO_PRIORITY_INFO structure is used to hold thread priority information.
old-location: ifsk\io_priority_info.htm
tech.root: ifsk
ms.assetid: 1161b239-3ad1-4a0c-9d11-4a3a88d361b3
ms.date: 04/16/2018
ms.keywords: "*PIO_PRIORITY_INFO, IO_PRIORITY_INFO, IO_PRIORITY_INFO structure [Installable File System Drivers], PIO_PRIORITY_INFO, PIO_PRIORITY_INFO structure pointer [Installable File System Drivers], _IO_PRIORITY_INFO, ifsk.io_priority_info, ntifs/IO_PRIORITY_INFO, ntifs/PIO_PRIORITY_INFO, othersystemstructures_19a36a9e-6950-4a52-b1e3-e25977777952.xml"
ms.topic: struct
f1_keywords:
 - "ntifs/IO_PRIORITY_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- IO_PRIORITY_INFO
product:
- Windows
targetos: Windows
req.typenames: IO_PRIORITY_INFO, *PIO_PRIORITY_INFO
---

# _IO_PRIORITY_INFO structure


## -description


The IO_PRIORITY_INFO structure is used to hold thread priority information.


## -struct-fields




### -field Size

Read-only member initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a> routine.


### -field ThreadPriority

Read-only member used to hold a thread's priority.


### -field PagePriority

Read-only member used to hold a thread's paging priority.


### -field IoPriority

Read-only member used to hold a thread's I/O priority.


## -remarks



The IO_PRIORITY_INFO structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a> routines to save and set a thread's priority state.

A structure of type IO_PRIORITY_INFO must be initialized before first use by calling either the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a> routine or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhint">FltGetIoPriorityHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetiopriorityhintintothread">FltSetIoPriorityHintIntoThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo">IoInitializePriorityInfo</a>
 

 

