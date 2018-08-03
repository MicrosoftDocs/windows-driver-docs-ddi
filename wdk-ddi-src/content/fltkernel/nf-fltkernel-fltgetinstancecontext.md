---
UID: NF:fltkernel.FltGetInstanceContext
title: FltGetInstanceContext function
author: windows-driver-content
description: The FltGetInstanceContext routine retrieves a context that was set for an instance by a given minifilter driver.
old-location: ifsk\fltgetinstancecontext.htm
tech.root: ifsk
ms.assetid: 74bbffcd-27a9-4a9e-b625-64f9860f2c66
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_8d05bb2a-ad52-454b-89d6-b15413c34e7f.xml, FltGetInstanceContext, FltGetInstanceContext routine [Installable File System Drivers], fltkernel/FltGetInstanceContext, ifsk.fltgetinstancecontext
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
-	FltGetInstanceContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetInstanceContext function


## -description


The <b>FltGetInstanceContext</b> routine retrieves a context that was set for an instance by a given minifilter driver. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the instance. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the instance context. 


## -returns



<b>FltGetInstanceContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching context was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetInstanceContext</b> retrieves a context that was set for an instance by a given minifilter driver. 

<b>FltGetInstanceContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. Thus every successful call to <b>FltGetInstanceContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for an instance, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544521">FltSetInstanceContext</a>. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete an instance context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541982">FltDeleteInstanceContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544521">FltSetInstanceContext</a>
 

 

