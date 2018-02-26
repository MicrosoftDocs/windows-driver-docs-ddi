---
UID: NF:fltkernel.FltRetrieveIoPriorityInfo
title: FltRetrieveIoPriorityInfo function
author: windows-driver-content
description: The FltRetrieveIoPriorityInfo routine is used by a minifilter driver to retrieve priority information from a thread.
old-location: ifsk\fltretrieveiopriorityinfo.htm
old-project: ifsk
ms.assetid: b764e55e-e58b-4a4f-a32f-84e3cfd5f8c4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FltApiRef_p_to_z_ac6da005-5f47-441d-8277-9beedb72c0ee.xml, FltRetrieveIoPriorityInfo, FltRetrieveIoPriorityInfo routine [Installable File System Drivers], I, P, R, e, f, fltkernel/FltRetrieveIoPriorityInfo, i, ifsk.fltretrieveiopriorityinfo, l, n, o, r, t, v, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	FltMgr.sys
apiname:
-	FltRetrieveIoPriorityInfo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltRetrieveIoPriorityInfo function


## -description


The <b>FltRetrieveIoPriorityInfo</b> routine is used by a minifilter driver to retrieve priority information from a thread.


## -syntax


````
NTSTATUS FltRetrieveIoPriorityInfo(
  _In_opt_ PFLT_CALLBACK_DATA Data,
  _In_opt_ PFILE_OBJECT       FileObject,
  _In_opt_ PETHREAD           Thread,
  _Inout_  PIO_PRIORITY_INFO  PriorityInfo
);
````


## -parameters




### -param Data [in, optional]


      An optional pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure, which represents an I/O operation.  This parameter can be <b>NULL</b>.
     


### -param FileObject [in, optional]

An optional pointer to the file object associated with the I/O operation.  This parameter can be <b>NULL</b>.


### -param Thread [in, optional]

An optional pointer to the thread in which to retrieve priority information from.  This parameter can be <b>NULL</b>.


### -param PriorityInfo [in, out]

A pointer to an <a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a> structure used to receive the priority information from the given thread.  The IO_PRIORITY_INFO structure must be initialized by an appropriate routine before it can be used by this routine. See the following Remarks section for more information.


## -returns



The <b>FltRetrieveIoPriorityInfo</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value.




## -remarks



The <b>FltRetrieveIoPriorityInfo</b> routine retrieves priority information and saves the information in the structure pointed to by the <i>PriorityInfo</i> parameter.

Typically, the <b>FltRetrieveIoPriorityInfo</b> routine is used in conjunction with the <a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a> routine to save and then set a thread's I/O priority, paging priority, and thread priority.

If the <i>Thread</i> parameter is non-<b>NULL</b>, the thread's paging priority and thread priority will be retrieved and placed in the <b>PagePriority</b> and <b>ThreadPriority</b> members of the IO_PRIORITY_INFO structure pointed to by the <i>PriorityInfo</i> parameter.  If the <i>Thread</i> parameter is <b>NULL</b>, the <b>ThreadPriority</b> and <b>PagePriority</b> members of the IO_PRIORITY_INFO structure are marked with sentinel values indicating that the thread's paging and thread priorities should not be changed by the system.  Note that these sentinel values stay in effect until explicitly changed.

The following pseudo-code example describes what I/O priority value is retrieved and placed in the <b>IoPriority</b> member of the IO_PRIORITY_INFO structure pointed to by the <i>PriorityInfo </i> parameter.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the normal I/O priority value.
IF Data is not NULL and represents an IRP-based operation and has I/O priority information available THEN
 Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the Data's I/O priority value.
ELSE 
 IF the FileObject parameter is not NULL and has I/O priority information available THEN
 Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the FileObject's I/O priority value.
 ELSE
 IF the Thread parameter is not NULL THEN
 Set the IoPriority member of the structure pointed to by the PriorityInfo parameter to the Thread's I/O priority value.</pre>
</td>
</tr>
</table></span></div>

<div class="alert"><b>Note</b>  
     If the IO_PRIORITY_INFO structure pointed to by the <i>PriorityInfo</i> parameter has not been initialized, you must do so prior to calling this routine, by calling the <a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a> routine.</div>
<div> </div>





## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a>



<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRetrieveIoPriorityInfo routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

