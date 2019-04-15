---
UID: NF:fltkernel.FltRetrieveIoPriorityInfo
title: FltRetrieveIoPriorityInfo function (fltkernel.h)
description: The FltRetrieveIoPriorityInfo routine is used by a minifilter driver to retrieve priority information from a thread.
old-location: ifsk\fltretrieveiopriorityinfo.htm
tech.root: ifsk
ms.assetid: b764e55e-e58b-4a4f-a32f-84e3cfd5f8c4
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_ac6da005-5f47-441d-8277-9beedb72c0ee.xml, FltRetrieveIoPriorityInfo, FltRetrieveIoPriorityInfo routine [Installable File System Drivers], fltkernel/FltRetrieveIoPriorityInfo, ifsk.fltretrieveiopriorityinfo
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- FltMgr.sys
api_name:
- FltRetrieveIoPriorityInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRetrieveIoPriorityInfo function


## -description


The <b>FltRetrieveIoPriorityInfo</b> routine is used by a minifilter driver to retrieve priority information from a thread.


## -parameters




### -param Data [in, optional]


      An optional pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure, which represents an I/O operation.  This parameter can be <b>NULL</b>.
     


### -param FileObject [in, optional]

An optional pointer to the file object associated with the I/O operation.  This parameter can be <b>NULL</b>.


### -param Thread [in, optional]

An optional pointer to the thread in which to retrieve priority information from.  This parameter can be <b>NULL</b>.


### -param PriorityInfo [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a> structure used to receive the priority information from the given thread.  The IO_PRIORITY_INFO structure must be initialized by an appropriate routine before it can be used by this routine. See the following Remarks section for more information.


## -returns



The <b>FltRetrieveIoPriorityInfo</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value.




## -remarks



The <b>FltRetrieveIoPriorityInfo</b> routine retrieves priority information and saves the information in the structure pointed to by the <i>PriorityInfo</i> parameter.

Typically, the <b>FltRetrieveIoPriorityInfo</b> routine is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a> routine to save and then set a thread's I/O priority, paging priority, and thread priority.

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
     If the IO_PRIORITY_INFO structure pointed to by the <i>PriorityInfo</i> parameter has not been initialized, you must do so prior to calling this routine, by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548424">IoInitializePriorityInfo</a> routine.</div>
<div> </div>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548424">IoInitializePriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
 

 

