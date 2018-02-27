---
UID: NC:storport.HW_DPC_ROUTINE
title: HW_DPC_ROUTINE
author: windows-driver-content
description: The HwStorDpcRoutine routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.
old-location: storage\hwstordpcroutine.htm
old-project: storage
ms.assetid: bc646191-e405-49e2-8793-0c0b81e52f50
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HW_DPC_ROUTINE, HwStorDpcRoutine, HwStorDpcRoutine routine [Storage Devices], storage.hwstordpcroutine, stormini_593e93b3-e078-48a4-b192-75cc161686bb.xml, storport/HwStorDpcRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorDpcRoutine
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_DPC_ROUTINE callback


## -description


The <b>HwStorDpcRoutine</b> routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism. 


## -prototype


````
HW_DPC_ROUTINE HwStorDpcRoutine;

VOID HwStorDpcRoutine(
   IN PSTOR_DPC Dpc,
   IN PVOID     HwDeviceExtension,
   IN PVOID     SystemArgument1,
   IN PVOID     SystemArgument2
)
{ ... }
````


## -parameters




### -param Dpc

A pointer to a Storport DPC  context. 


### -param HwDeviceExtension

A pointer to the per-adapter device extension. 


### -param SystemArgument1

A pointer to caller-supplied information.


### -param SystemArgument2

A pointer to caller-supplied information.


## -returns



None. 




## -remarks



When a miniport driver calls <a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a> to initialize a DPC it must load the <i>HwDpcRoutine</i>  parameter of the <b>StorPortInitializeDpc</b> routine with a pointer to the <b>HwStorDpcRoutine</b> routine. 

Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> routine or with the <a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a> routine by acquiring the appropriate spin lock with a call to <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>. For more information about the management of spin locks within DPC routines, see <a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>. 

The name <b>HwStorDpcRoutine</b> is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
HW_DPC_ROUTINE (
  _In_  PSTOR_DPC Dpc,
  _In_  PVOID HwDeviceExtension,
  _In_opt_  PVOID SystemArgument1,
  _In_opt_  PVOID SystemArgument2
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the <b>HwStorDpcRoutine</b> routine at DISPATCH IRQL.


#### Examples

To define an <b>HwStorDpcRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorDpcRoutine</b> callback routine that is named <i>MyHwDpcRoutine</i>, use the <b>HW_DPC_ROUTINE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_DPC_ROUTINE MyHwDpcRoutine;</pre>
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
BOOLEAN
MyHwDpcRoutine (
  _In_  PSTOR_DPC Dpc,
  _In_  PVOID HwDeviceExtension,
  _In_opt_  PVOID SystemArgument1,
  _In_opt_  PVOID SystemArgument2
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_DPC_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_DPC_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also

<a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a>



<a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>



<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>



<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>



<a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_DPC_ROUTINE routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

