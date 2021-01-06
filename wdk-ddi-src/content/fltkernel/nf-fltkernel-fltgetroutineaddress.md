---
UID: NF:fltkernel.FltGetRoutineAddress
title: FltGetRoutineAddress function (fltkernel.h)
description: The FltGetRoutineAddress routine returns a pointer to a routine specified by the FltMgrRoutineName parameter.
old-location: ifsk\fltgetroutineaddress.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetRoutineAddress function"]
ms.keywords: FltApiRef_e_to_o_81848969-38e3-4f2f-bdc3-45027ea28202.xml, FltGetRoutineAddress, FltGetRoutineAddress routine [Installable File System Drivers], fltkernel/FltGetRoutineAddress, ifsk.fltgetroutineaddress
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetRoutineAddress
 - fltkernel/FltGetRoutineAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetRoutineAddress
---

# FltGetRoutineAddress function


## -description

The <b>FltGetRoutineAddress</b> routine returns a pointer to a routine specified by the <i>FltMgrRoutineName</i> parameter.

## -parameters

### -param FltMgrRoutineName 

[in]
Name of the filter manager routine to resolve.

## -returns

If the routine name can be resolved, <b>FltGetRoutineAddress</b> returns a pointer to the routine. Otherwise, it returns <b>NULL</b>.

## -remarks

<b>FltGetRoutineAddress</b> searches the filter manager's export table for the requested routine name. 

To get the addresses of other routines that are exported by the kernel or hardware abstraction layer (HAL), use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemroutineaddress">MmGetSystemRoutineAddress</a>. 

Note that in Windows 2000 and Windows XP, before FltGetRoutineAddress is called at least one minifilter on the system must call FltRegisterFilter. The call to FltRegisterFilter is necessary to initialize global data structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemroutineaddress">MmGetSystemRoutineAddress</a>
