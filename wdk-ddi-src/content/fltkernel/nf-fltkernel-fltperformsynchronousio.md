---
UID: NF:fltkernel.FltPerformSynchronousIo
title: FltPerformSynchronousIo function
description: A minifilter driver calls FltPerformSynchronousIo to initiate a synchronous I/O operation after calling FltAllocateCallbackData to allocate a callback data structure for the operation.
old-location: ifsk\fltperformsynchronousio.htm
tech.root: ifsk
ms.assetid: 14f5260a-b18d-4329-a81e-d24026d9a71d
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_02aeeeab-6a33-4336-aaa4-810bd70850bc.xml, FltPerformSynchronousIo, FltPerformSynchronousIo routine [Installable File System Drivers], fltkernel/FltPerformSynchronousIo, ifsk.fltperformsynchronousio
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltPerformSynchronousIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltPerformSynchronousIo function


## -description


A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a> to allocate a callback data structure for the operation. 


## -parameters




### -param CallbackData [in, out]

Pointer to a callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. The caller is responsible for freeing this structure when it is no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a>. 


## -returns



None 




## -remarks



A minifilter driver calls <b>FltPerformSynchronousIo</b> to initiate a synchronous I/O operation. 

Minifilter drivers can only initiate IRP-based I/O operations. They cannot initiate fast I/O or file system filter (FSFilter) callback operations. 

<b>FltPerformSynchronousIo</b> sends the I/O operation only to the minifilter driver instances attached below the initiating instance (specified in the <i>Instance</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>), and the file system. Minifilter drivers attached above the specified instance do not receive the I/O operation. 

Minifilter drivers should use <b>FltPerformSynchronousIo</b> only in cases where routines such as the following cannot be used: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543439">FltQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544564">FltSetVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544610">FltWriteFile</a>


After <b>FltPerformSynchronousIo</b> returns, the caller can reissue the I/O operation by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544311">FltReissueSynchronousIo</a>. Alternatively, the caller can free the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a> or prepare it to be reused by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544358">FltReuseCallbackData</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541703">FltAllocateCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542949">FltFreeCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543420">FltPerformAsynchronousIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543439">FltQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544311">FltReissueSynchronousIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544358">FltReuseCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544564">FltSetVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544610">FltWriteFile</a>
 

 

