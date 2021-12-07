---
UID: NF:fltkernel.FltIs32bitProcess
title: FltIs32bitProcess function (fltkernel.h)
description: The FltIs32bitProcess routine checks whether the originator of the current I/O operation is a 32-bit user-mode application.
old-location: ifsk\fltis32bitprocess.htm
tech.root: ifsk
ms.date: 11/29/2021
keywords: ["FltIs32bitProcess function"]
ms.keywords: FltApiRef_e_to_o_dbd737ec-e787-4f85-bd9e-833e06e862f0.xml, FltIs32bitProcess, FltIs32bitProcess routine [Installable File System Drivers], fltkernel/FltIs32bitProcess, ifsk.fltis32bitprocess
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Microsoft Windows XP SP2
req.target-min-winversvr: Microsoft Windows Server 2003 SP1
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltIs32bitProcess
 - fltkernel/FltIs32bitProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltIs32bitProcess
---

# FltIs32bitProcess function

## -description

The **FltIs32bitProcess** routine checks whether the originator of the current I/O operation is a 32-bit user-mode application.

## -parameters

### -param CallbackData [in, optional]

Pointer to the callback data structure for the current I/O operation ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)). This parameter is optional and can be **NULL**.

## -returns

**FltIs32bitProcess** returns **TRUE** if the originator of the current I/O operation is a 32-bit user-mode process, **FALSE** otherwise.

## -remarks

Minifilter drivers call **FltIs32bitProcess** to determine whether an I/O request is likely to contain data elements that need to be converted, or "thunked," before they can be used in a 64-bit driver. For more information about thunking and other 64-bit driver issues, see [Programming Issues for 64-Bit Drivers](/windows-hardware/drivers/kernel/programming-issues-for-64-bit-drivers).

On a 32-bit system, **FltIs32bitProcess** always returns **TRUE**.

On a 64-bit system, **FltIs32bitProcess** returns **TRUE** or **FALSE**, according to the following conditions:

* If the **CallbackData** parameter is **NULL**, and the caller is running in the context of a 32-bit user-mode process, **FltIs32bitProcess** returns **TRUE**.

* If the **CallbackData** parameter is not **NULL**, and the callback data structure represents an IRP-based I/O operation where IRP was issued by the I/O manager on behalf of a user-mode process, **FltIs32bitProcess** returns **TRUE**.

* If the **CallbackData** parameter is not **NULL**, the callback data structure represents a fast I/O operation or a file system filter (FSFilter) callback operation, and the caller is running in the context of a 32-bit user-mode process, **FltIs32bitProcess** returns **TRUE**.

* If none of the above conditions is **true**, **FltIs32bitProcess** returns **FALSE**.

To determine whether a callback data structure represents an IRP-based I/O operation, use the [**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85)) macro.

To determine whether a callback data structure represents a fast I/O operation, use the [**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md) macro.

To determine whether a callback data structure represents a file system filter (FSFilter) callback operation, use the [**FLT_IS_FS_FILTER_OPERATION**](/previous-versions/ff544648(v=vs.85)) macro.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](/previous-versions/ff544648(v=vs.85))

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**IoIs32bitProcess**](../wdm/nf-wdm-iois32bitprocess.md)
