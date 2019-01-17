---
UID: NC:wdfrequest.EVT_WDF_REQUEST_IMPERSONATE
title: EVT_WDF_REQUEST_IMPERSONATE
description: A driver's EvtRequestImpersonate event callback function performs tasks at the requested impersonation level, such as opening a protected file.
old-location: wdf\evtrequestimpersonate.htm
tech.root: wdf
ms.assetid: FA3FE0C0-57EC-4761-991B-49CA65A79BDD
ms.date: 02/26/2018
ms.keywords: EVT_WDF_REQUEST_IMPERSONATE, EVT_WDF_REQUEST_IMPERSONATE callback, EvtRequestImpersonate, EvtRequestImpersonate callback function, wdf.evtrequestimpersonate, wdfrequest/EvtRequestImpersonate
ms.topic: callback
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfrequest.h
api_name:
-	EvtRequestImpersonate
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_REQUEST_IMPERSONATE callback function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

A driver's <i>EvtRequestImpersonate</i> event callback function performs tasks at the requested impersonation level, such as opening a protected file.


## -parameters




### -param Request [in]

A handle to a framework request object that represents the I/O request that requires impersonation.


### -param Context [in, optional]

A pointer to a context that was previously supplied in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265619">WdfRequestImpersonate</a> method. This parameter is optional and can be NULL if a context is not required. 




## -returns



This callback function does not return a value.




## -remarks



User-Mode Driver Framework (UMDF) does not allow a driver's <i>EvtRequestImpersonate</i> callback function to call any of the framework's object methods. This ensures that the driver does not expose the impersonation level to other driver callback functions or other drivers.

For more information, see <a href="https://msdn.microsoft.com/02EA93CE-3C4D-4F6F-8E58-DD78EBDB19DE">Handling Client Impersonation in UMDF Drivers</a>.


#### Examples

To define an <i>EvtRequestImpersonate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtRequestImpersonate</i> callback function that is named <i>MyRequestImpersonate</i>, use the <b>EVT_WDF_REQUEST_IMPERSONATE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_REQUEST_IMPERSONATE  MyRequestImpersonate;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyRequestImpersonate (
    WDFREQUEST  Request
    PVOID  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_REQUEST_IMPERSONATE</b> function type is defined in the Wdfrequest.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_REQUEST_IMPERSONATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265619">WdfRequestImpersonate</a>
 

 

