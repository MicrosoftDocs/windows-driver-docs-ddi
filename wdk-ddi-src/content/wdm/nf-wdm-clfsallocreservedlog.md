---
UID: NF:wdm.ClfsAllocReservedLog
title: ClfsAllocReservedLog function (wdm.h)
description: The ClfsAllocReservedLog routine reserves space in a marshalling area for a set of records.
old-location: kernel\clfsallocreservedlog.htm
tech.root: kernel
ms.assetid: 05e4fb47-38ef-4b46-a1bb-220c5b1a63ca
ms.date: 04/30/2018
keywords: ["ClfsAllocReservedLog function"]
ms.keywords: ClfsAllocReservedLog, ClfsAllocReservedLog routine [Kernel-Mode Driver Architecture], Clfs_4429c61b-96d5-48cb-9ff0-5b0e3f01e0ec.xml, kernel.clfsallocreservedlog, wdm/ClfsAllocReservedLog
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsAllocReservedLog
 - wdm/ClfsAllocReservedLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsAllocReservedLog
---

# ClfsAllocReservedLog function


## -description

The <b>ClfsAllocReservedLog</b> routine reserves space in a marshalling area for a set of records.

## -parameters

### -param pvMarshalContext 

[in]
A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.

### -param cRecords 

[in]
The number of records in the set. This value must match the value of <i>cRecords</i> previously passed to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsalignreservedlog">ClfsAlignReservedLog</a>.

### -param pcbAdjustment 

[in]
A pointer to a LONGLONG-typed variable that supplies the size, in bytes, of the reservation that will hold all the records in the set. The caller previously obtained this size by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsalignreservedlog">ClfsAlignReservedLog</a>.

## -returns

<b>ClfsAllocReservedLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

For an explanation of CLFS concepts and terminology, see <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsalignreservedlog">ClfsAlignReservedLog</a>