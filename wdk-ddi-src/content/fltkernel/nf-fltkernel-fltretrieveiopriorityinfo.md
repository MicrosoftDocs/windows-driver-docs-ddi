---
UID: NF:fltkernel.FltRetrieveIoPriorityInfo
title: FltRetrieveIoPriorityInfo function (fltkernel.h)
description: The FltRetrieveIoPriorityInfo routine is used by a minifilter driver to retrieve priority information from a thread.
old-location: ifsk\fltretrieveiopriorityinfo.htm
tech.root: ifsk
ms.assetid: b764e55e-e58b-4a4f-a32f-84e3cfd5f8c4
ms.date: 04/16/2018
keywords: ["FltRetrieveIoPriorityInfo function"]
ms.keywords: FltApiRef_p_to_z_ac6da005-5f47-441d-8277-9beedb72c0ee.xml, FltRetrieveIoPriorityInfo, FltRetrieveIoPriorityInfo routine [Installable File System Drivers], fltkernel/FltRetrieveIoPriorityInfo, ifsk.fltretrieveiopriorityinfo
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: Fltmgr.lib
req.dll: FltMgr.sys
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltRetrieveIoPriorityInfo
 - fltkernel/FltRetrieveIoPriorityInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltRetrieveIoPriorityInfo
---

# FltRetrieveIoPriorityInfo function

## -description

The **FltRetrieveIoPriorityInfo** routine is used by a minifilter driver to retrieve priority information from a thread.

## -parameters

### -param Data

[in, optional] An optional pointer to a [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure, which represents an I/O operation.  This parameter can be **NULL**.

### -param FileObject

[in, optional] An optional pointer to the file object associated with the I/O operation.  This parameter can be **NULL**.

### -param Thread

[in, optional] An optional pointer to the thread in which to retrieve priority information from.  This parameter can be **NULL**.

### -param PriorityInfo

[in, out] A pointer to an [**IO_PRIORITY_INFO**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info) structure used to receive the priority information from the given thread.  The IO_PRIORITY_INFO structure must be initialized by an appropriate routine before it can be used by this routine. See the following Remarks section for more information.

## -returns

The **FltRetrieveIoPriorityInfo** routine returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks

The **FltRetrieveIoPriorityInfo** routine retrieves priority information and saves the information in the structure pointed to by the **PriorityInfo** parameter.

Typically, the **FltRetrieveIoPriorityInfo** routine is used in conjunction with the [**FltApplyPriorityInfoThread**](nf-fltkernel-fltapplypriorityinfothread.md) routine to save and then set a thread's I/O priority, paging priority, and thread priority.

If the **Thread** parameter is non-**NULL**, the thread's paging priority and thread priority will be retrieved and placed in the **PagePriority** and **ThreadPriority** members of the IO_PRIORITY_INFO structure pointed to by the **PriorityInfo** parameter.  If the **Thread** parameter is **NULL**, the **ThreadPriority** and **PagePriority** members of the IO_PRIORITY_INFO structure are marked with sentinel values indicating that the thread's paging and thread priorities should not be changed by the system.  Note that these sentinel values stay in effect until explicitly changed.

The following pseudo-code example describes what I/O priority value is retrieved and placed in the **IoPriority** member of the IO_PRIORITY_INFO structure pointed to by the **PriorityInfo** parameter.

```
Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the normal I/O priority value.
IF Data is not NULL and represents an IRP-based operation and has I/O priority information available THEN
    Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the Data's I/O priority value.
ELSE IF the FileObject parameter is not NULL and has I/O priority information available THEN
    Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the FileObject's I/O priority value.
ELSE IF the Thread parameter is not NULL THEN
    Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the Thread's I/O priority value.
```

> [!NOTE]
> If the IO_PRIORITY_INFO structure pointed to by the **PriorityInfo** parameter has not been initialized, you must do so prior to calling this routine, by calling the [**IoInitializePriorityInfo**](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo) routine.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FltApplyPriorityInfoThread**](nf-fltkernel-fltapplypriorityinfothread.md)

[**FltGetIoPriorityHint**](nf-fltkernel-fltgetiopriorityhint.md)

[**FltGetIoPriorityHintFromCallbackData**](nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md)

[**FltGetIoPriorityHintFromFileObject**](nf-fltkernel-fltgetiopriorityhintfromfileobject.md)

[**FltGetIoPriorityHintFromThread**](nf-fltkernel-fltgetiopriorityhintfromthread.md)

[**FltRetrieveIoPriorityInfo**](nf-fltkernel-fltretrieveiopriorityinfo.md)

[**FltSetIoPriorityHintIntoCallbackData**](nf-fltkernel-fltsetiopriorityhintintocallbackdata.md)

[**FltSetIoPriorityHintIntoFileObject**](nf-fltkernel-fltsetiopriorityhintintofileobject.md)

[**FltSetIoPriorityHintIntoThread**](nf-fltkernel-fltsetiopriorityhintintothread.md)

[**IO_PRIORITY_INFO**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_io_priority_info)

[**IoInitializePriorityInfo**](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioinitializepriorityinfo)

[**PsGetCurrentThread**](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread)
