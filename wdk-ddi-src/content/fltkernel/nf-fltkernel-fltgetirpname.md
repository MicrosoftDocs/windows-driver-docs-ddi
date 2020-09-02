---
UID: NF:fltkernel.FltGetIrpName
title: FltGetIrpName function (fltkernel.h)
description: The FltGetIrpName routine returns the name for a major function code as a printable string.
old-location: ifsk\fltgetirpname.htm
tech.root: ifsk
ms.assetid: d4087825-cdfd-4de5-a5b7-f95f6f0563e6
ms.date: 04/16/2018
keywords: ["FltGetIrpName function"]
ms.keywords: FltApiRef_e_to_o_35d2b6e8-d233-4c6e-a27a-6a5770f5f5d0.xml, FltGetIrpName, FltGetIrpName routine [Installable File System Drivers], fltkernel/FltGetIrpName, ifsk.fltgetirpname
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetIrpName
 - fltkernel/FltGetIrpName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetIrpName
---

# FltGetIrpName function


## -description

The <b>FltGetIrpName</b> routine returns the name for a major function code as a printable string.

## -parameters

### -param IrpMajorCode 

[in]
The IRP major function code whose name is to be returned.

## -returns

If <i>IrpMajorCode</i> is a valid major function code value, <b>FltGetIrpName</b> returns its name as a null-terminated string of ANSI characters (such as "IRP_MJ_CREATE"). Otherwise, <b>FltGetIrpName</b> returns "<invalid IRP code>".

## -remarks

<b>FltGetIrpName</b> is a debugging support routine. 

The value of the <i>IrpMajorCode</i> parameter can equal to the value of the <b>MajorFunction</b> field for an IRP or the <b>MajorFunction</b> field for the <b>Iopb</b> field of a callback data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>

