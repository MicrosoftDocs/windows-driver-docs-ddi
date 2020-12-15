---
UID: NF:fltkernel.FltAllocateCallbackData
title: FltAllocateCallbackData function (fltkernel.h)
description: FltAllocateCallbackData allocates a callback data structure that a minifilter driver can use to initiate an I/O request.
old-location: ifsk\fltallocatecallbackdata.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltAllocateCallbackData function"]
ms.keywords: FltAllocateCallbackData, FltAllocateCallbackData routine [Installable File System Drivers], FltApiRef_a_to_d_74309bb1-841a-41a6-bd3e-71ed710bc727.xml, fltkernel/FltAllocateCallbackData, ifsk.fltallocatecallbackdata
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAllocateCallbackData
 - fltkernel/FltAllocateCallbackData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAllocateCallbackData
---

# FltAllocateCallbackData function


## -description

<b>FltAllocateCallbackData</b> allocates a callback data structure that a minifilter driver can use to initiate an I/O request.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the minifilter driver instance that is initiating the I/O operation. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in, optional]
File object pointer to be used in the I/O operation. This parameter is optional and can be <b>NULL</b>.

### -param RetNewCallbackData 

[out]
Pointer to a caller-allocated variable that receives the address of the newly allocated callback data (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure.

## -returns

<b>FltAllocateCallbackData</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdata">FltAllocateCallbackData</a> encountered a pool allocation failure when attempting to allocate the callback data structure. This is an error code. 

</td>
</tr>
</table>

## -remarks

A minifilter driver can call <b>FltAllocateCallbackData</b> to allocate a callback data (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for an I/O operation initiated by the minifilter driver. 

<div class="alert"><b>Note</b>  The <b>FltAllocateCallbackData</b> routine does not allocate all the memory that might be required by a subsequent I/O request. If an I/O request, such as <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a> or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>, requires additional memory for some structure, the request could encounter a memory allocation. The <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecallbackdataex">FltAllocateCallbackDataEx</a> routine can be used to avoid this potential problem by preallocating memory for additional structures to be used in an I/O request. If there is a memory allocation problem for either the <i>RetNewCallbackData</i> structure or additional required structures, it can be dealt with at the point of callback data allocation.</div>
<div> </div>
Callback data structures are allocated from nonpaged pool. 

After initializing the parameters of the callback data structure returned by <b>FltAllocateCallbackData</b>, the caller initiates the I/O operation by passing the structure to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a> or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>. These routines send the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter) and to the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

Minifilter drivers should use <b>FltAllocateCallbackData</b>, <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>, and <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a> only for I/O operations for which routines such as the following cannot be used: 


<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose">FltClose</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>


When the callback data structure allocated by <b>FltAllocateCallbackData</b> is no longer needed, the caller is responsible for freeing it by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose">FltClose</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreecallbackdata">FltFreeCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformasynchronousio">FltPerformAsynchronousIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltperformsynchronousio">FltPerformSynchronousIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile">FltReadFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreusecallbackdata">FltReuseCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetvolumeinformation">FltSetVolumeInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile">FltWriteFile</a>
