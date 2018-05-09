---
UID: NF:fltkernel.FltIs32bitProcess
title: FltIs32bitProcess function
author: windows-driver-content
description: The FltIs32bitProcess routine checks whether the originator of the current I/O operation is a 32-bit user-mode application.
old-location: ifsk\fltis32bitprocess.htm
old-project: ifsk
ms.assetid: 0ba4d101-5eba-4258-9526-9e9dc3fd142a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_dbd737ec-e787-4f85-bd9e-833e06e862f0.xml, FltIs32bitProcess, FltIs32bitProcess routine [Installable File System Drivers], fltkernel/FltIs32bitProcess, ifsk.fltis32bitprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltIs32bitProcess routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
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
-	FltIs32bitProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIs32bitProcess function


## -description


The <b>FltIs32bitProcess</b> routine checks whether the originator of the current I/O operation is a 32-bit user-mode application.


## -parameters




### -param CallbackData [in, optional]

Pointer to the callback data structure for the current I/O operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltIs32bitProcess</b> returns <b>TRUE</b> if the originator of the current I/O operation is a 32-bit user-mode process, <b>FALSE</b> otherwise.




## -remarks



Minifilter drivers call <b>FltIs32bitProcess</b> to determine whether an I/O request is likely to contain data elements that need to be converted, or "thunked," before they can be used in a 64-bit driver. For more information about thunking and other 64-bit driver issues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559923">Programming Issues for 64-Bit Drivers</a>. 

On a 32-bit system, <b>FltIs32bitProcess</b> always returns <b>TRUE</b>. 

On a 64-bit system, <b>FltIs32bitProcess</b> returns <b>TRUE</b> or <b>FALSE</b>, according to the following conditions: 

<ul>
<li>
If the <i>CallbackData</i> parameter is <b>NULL</b>, and the caller is running in the context of a 32-bit user-mode process, <b>FltIs32bitProcess</b> returns <b>TRUE</b>. 

</li>
<li>
If the <i>CallbackData</i> parameter is not <b>NULL</b>, and the callback data structure represents an IRP-based I/O operation where IRP was issued by the I/O manager on behalf of a user-mode process, <b>FltIs32bitProcess</b> returns <b>TRUE</b>. 

</li>
<li>
If the <i>CallbackData</i> parameter is not <b>NULL</b>, the callback data structure represents a fast I/O operation or a file system filter (FSFilter) callback operation, and the caller is running in the context of a 32-bit user-mode process, <b>FltIs32bitProcess</b> returns <b>TRUE</b>. 

</li>
<li>
If none of the above conditions is <b>true</b>, <b>FltIs32bitProcess</b> returns <b>FALSE</b>. 

</li>
</ul>
To determine whether a callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

To determine whether a callback data structure represents a fast I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a> macro. 

To determine whether a callback data structure represents a file system filter (FSFilter) callback operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544648">FLT_IS_FS_FILTER_OPERATION</a> macro.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544648">FLT_IS_FS_FILTER_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549372">IoIs32bitProcess</a>
 

 

