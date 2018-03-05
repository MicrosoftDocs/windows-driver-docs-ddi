---
UID: NF:fltkernel.FltAllocateCallbackData
title: FltAllocateCallbackData function
author: windows-driver-content
description: FltAllocateCallbackData allocates a callback data structure that a minifilter driver can use to initiate an I/O request.
old-location: ifsk\fltallocatecallbackdata.htm
old-project: ifsk
ms.assetid: a2afb8b8-b0e2-4d22-9d93-33ba2b2f8933
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltAllocateCallbackData, FltAllocateCallbackData routine [Installable File System Drivers], FltApiRef_a_to_d_74309bb1-841a-41a6-bd3e-71ed710bc727.xml, fltkernel/FltAllocateCallbackData, ifsk.fltallocatecallbackdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAllocateCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocateCallbackData function


## -description


<b>FltAllocateCallbackData</b> allocates a callback data structure that a minifilter driver can use to initiate an I/O request. 


## -syntax


````
NTSTATUS FltAllocateCallbackData(
  _In_     PFLT_INSTANCE      Instance,
  _In_opt_ PFILE_OBJECT       FileObject,
  _Out_    PFLT_CALLBACK_DATA *RetNewCallbackData
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that is initiating the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in, optional]

File object pointer to be used in the I/O operation. This parameter is optional and can be <b>NULL</b>. 


### -param RetNewCallbackData [out]

Pointer to a caller-allocated variable that receives the address of the newly allocated callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure. 


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

<a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a> encountered a pool allocation failure when attempting to allocate the callback data structure. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver can call <b>FltAllocateCallbackData</b> to allocate a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for an I/O operation initiated by the minifilter driver. 

<div class="alert"><b>Note</b>  The <b>FltAllocateCallbackData</b> routine does not allocate all the memory that might be required by a subsequent I/O request. If an I/O request, such as <a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a> or <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>, requires additional memory for some structure, the request could encounter a memory allocation. The <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdataex.md">FltAllocateCallbackDataEx</a> routine can be used to avoid this potential problem by preallocating memory for additional structures to be used in an I/O request. If there is a memory allocation problem for either the <i>RetNewCallbackData</i> structure or additional required structures, it can be dealt with at the point of callback data allocation.</div>
<div> </div>
Callback data structures are allocated from nonpaged pool. 

After initializing the parameters of the callback data structure returned by <b>FltAllocateCallbackData</b>, the caller initiates the I/O operation by passing the structure to <a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a> or <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>. These routines send the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter) and to the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

Minifilter drivers should use <b>FltAllocateCallbackData</b>, <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>, and <a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a> only for I/O operations for which routines such as the following cannot be used: 


<a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>


When the callback data structure allocated by <b>FltAllocateCallbackData</b> is no longer needed, the caller is responsible for freeing it by calling <a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltreusecallbackdata.md">FltReuseCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>



<a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateCallbackData routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

