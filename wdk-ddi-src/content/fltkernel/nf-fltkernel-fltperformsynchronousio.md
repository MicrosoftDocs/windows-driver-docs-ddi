---
UID: NF:fltkernel.FltPerformSynchronousIo
title: FltPerformSynchronousIo function (fltkernel.h)
description: A minifilter driver calls FltPerformSynchronousIo to initiate a synchronous I/O operation after calling FltAllocateCallbackData to allocate a callback data structure for the operation.
old-location: ifsk\fltperformsynchronousio.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltPerformSynchronousIo function"]
ms.keywords: FltApiRef_p_to_z_02aeeeab-6a33-4336-aaa4-810bd70850bc.xml, FltPerformSynchronousIo, FltPerformSynchronousIo routine [Installable File System Drivers], fltkernel/FltPerformSynchronousIo, ifsk.fltperformsynchronousio
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltPerformSynchronousIo
 - fltkernel/FltPerformSynchronousIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltPerformSynchronousIo
---

# FltPerformSynchronousIo function


## -description

A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation after calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> to allocate a callback data structure for the operation.

## -parameters

### -param CallbackData 

[in, out]
Pointer to a callback data (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure allocated by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. The caller is responsible for freeing this structure when it is no longer needed by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a>.

## -returns

None

## -remarks

A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

<b>FltPerformSynchronousIo</b> sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers should use <b>FltPerformSynchronousIo</b> only in cases where routines such as the following cannot be used: 


<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose">FltClose</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>


After <b>FltPerformSynchronousIo</b> returns, the caller can reissue the I/O operation by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>. Alternatively, the caller can free the callback data (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a> or prepare it to be reused by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose">FltClose</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile">FltSetInformationFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>
