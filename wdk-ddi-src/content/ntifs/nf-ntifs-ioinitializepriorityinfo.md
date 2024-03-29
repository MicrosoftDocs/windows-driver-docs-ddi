---
UID: NF:ntifs.IoInitializePriorityInfo
title: IoInitializePriorityInfo function (ntifs.h)
description: The IoInitializePriorityInfo routine initializes a structure of type IO_PRIORITY_INFO.
old-location: ifsk\ioinitializepriorityinfo.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoInitializePriorityInfo function"]
ms.keywords: IoInitializePriorityInfo, IoInitializePriorityInfo routine [Installable File System Drivers], ifsk.ioinitializepriorityinfo, ioref_65eef333-11a8-4603-9b64-dc317f3d4e7b.xml, ntifs/IoInitializePriorityInfo
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoInitializePriorityInfo
 - ntifs/IoInitializePriorityInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IoInitializePriorityInfo
---

# IoInitializePriorityInfo function


## -description

The <b>IoInitializePriorityInfo</b> routine initializes a structure of type <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>.

## -parameters

### -param PriorityInfo [in]


Pointer to a structure, of type IO_PRIORITY_INFO, to be initialized. This parameter is required and cannot be <b>NULL</b>.

## -remarks

The <b>IoInitializePriorityInfo</b> routine is used to initialize the IO_PRIORITY_INFO structure that is utilized by the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info">IO_PRIORITY_INFO</a>
