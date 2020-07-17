---
UID: NF:fltkernel.FltGetNewSystemBufferAddress
title: FltGetNewSystemBufferAddress function (fltkernel.h)
description: The FltGetNewSystemBufferAddress function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function.
old-location: ifsk\fltgetnewsystembufferaddress.htm
tech.root: ifsk
ms.assetid: 83a5e9b7-1731-422f-a0df-c1efbc8cad81
ms.date: 04/16/2018
keywords: ["FltGetNewSystemBufferAddress function"]
ms.keywords: FltApiRef_e_to_o_a9a2a8aa-92e5-4843-a1e9-5b1a15d870fa.xml, FltGetNewSystemBufferAddress, FltGetNewSystemBufferAddress function [Installable File System Drivers], fltkernel/FltGetNewSystemBufferAddress, ifsk.fltgetnewsystembufferaddress
f1_keywords:
 - "fltkernel/FltGetNewSystemBufferAddress"
 - "FltGetNewSystemBufferAddress"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 7 and later versions of the Windows operating system.
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
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetNewSystemBufferAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetNewSystemBufferAddress function


## -description


The <b>FltGetNewSystemBufferAddress</b> function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function. 


## -parameters




### -param CallbackData [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents an I/O operation.


## -returns



If the AssociatedIrp.SystemBuffer buffer was allocated by the file system, <b>FltGetNewSystemBufferAddress</b> returns a pointer to this buffer; otherwise it returns <b>NULL</b>.




## -remarks



A minifilter driver's post-callback routine calls <b>FltGetNewSystemBufferAddress</b> function to retrieve a pointer to the AssociatedIrp.SystemBuffer buffer that the file system has allocated.  A minifilter driver should call this function only when the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag is set in <i>CallbackData.Flags</i>. 

When the file system allocates its own AssociatedIrp.SystemBuffer buffer, Filter Manager will set the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag.  This signals the minifilter that the buffer they received in the pre-operation is not the one that has the data read from the file system. 

If the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag is not set, then this routine returns <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>
 

 

