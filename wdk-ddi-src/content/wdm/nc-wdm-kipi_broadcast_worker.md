---
UID: NC:wdm.KIPI_BROADCAST_WORKER
title: KIPI_BROADCAST_WORKER
author: windows-driver-content
description: The IpiGenericCall routine runs simultaneously on all processors.
old-location: kernel\ipigenericcall.htm
old-project: kernel
ms.assetid: 7c4e3d6b-e000-4ac4-b200-966689d05426
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: DrvrRtns_80b940d9-3d19-4525-af3f-8e4058c57ddc.xml, IpiGenericCall, IpiGenericCall routine [Kernel-Mode Driver Architecture], KIPI_BROADCAST_WORKER, kernel.ipigenericcall, wdm/IpiGenericCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Called at IPI_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	IpiGenericCall
product: Windows
targetos: Windows
req.typenames: 
---

# KIPI_BROADCAST_WORKER callback function


## -description


The <i>IpiGenericCall</i> routine runs simultaneously on all processors.


## -parameters




### -param Argument [in]

Supplies the value that was passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552198">KeIpiGenericCall</a> routine that called <i>IpiGenericCall</i>.


## -returns



<i>IpiGenericCall</i> returns a driver-defined value. If <i>IpiGenericCall</i> ran on the same processor that called <b>KeIpiGenericCall</b>, <b>KeIpiGenericCall</b> returns the driver-defined value that <i>IpiGenericCall</i> returns. Otherwise, the value is ignored. 




## -remarks



<i>IpiGenericCall</i> routines run at IRQL = IPI_LEVEL, which is greater than DIRQL for every device. <i>IpiGenericCall</i> routines must satisfy the same restrictions as bug check callback routines. For more information about these restrictions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>.


#### Examples

To define an <i>IpiGenericCall</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>IpiGenericCall</i> callback routine that is named <code>MyIpiGenericCall</code>, use the KIPI_BROADCAST_WORKER type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KIPI_BROADCAST_WORKER MyIpiGenericCall;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
ULONG_PTR
  MyIpiGenericCall(
    ULONG_PTR  Argument
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The KIPI_BROADCAST_WORKER function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KIPI_BROADCAST_WORKER function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552198">KeIpiGenericCall</a>
 

 

