---
UID: NC:storport.HW_DPC_ROUTINE
title: HW_DPC_ROUTINE (storport.h)
description: The HwStorDpcRoutine routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.
old-location: storage\hwstordpcroutine.htm
tech.root: storage
ms.assetid: bc646191-e405-49e2-8793-0c0b81e52f50
ms.date: 03/29/2018
keywords: ["HW_DPC_ROUTINE callback function"]
ms.keywords: HW_DPC_ROUTINE, HwStorDpcRoutine, HwStorDpcRoutine routine [Storage Devices], storage.hwstordpcroutine, stormini_593e93b3-e078-48a4-b192-75cc161686bb.xml, storport/HwStorDpcRoutine
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
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_DPC_ROUTINE
 - storport/HW_DPC_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HwStorDpcRoutine
---

# HW_DPC_ROUTINE callback function


## -description

The <b>HwStorDpcRoutine</b> routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.

## -parameters

### -param Dpc

A pointer to a Storport DPC  context.

### -param HwDeviceExtension

A pointer to the per-adapter device extension.

### -param SystemArgument1

A pointer to caller-supplied information.

### -param SystemArgument2

A pointer to caller-supplied information.

## -remarks

When a miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializedpc">StorPortInitializeDpc</a> to initialize a DPC it must load the <i>HwDpcRoutine</i>  parameter of the <b>StorPortInitializeDpc</b> routine with a pointer to the <b>HwStorDpcRoutine</b> routine. 

Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine or with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a> routine by acquiring the appropriate spin lock with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>. For more information about the management of spin locks within DPC routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportissuedpc">StorPortIssueDpc</a>. 

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

To define an <b>HwStorDpcRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

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
The <b>HW_DPC_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_DPC_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializedpc">StorPortInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportissuedpc">StorPortIssueDpc</a>

