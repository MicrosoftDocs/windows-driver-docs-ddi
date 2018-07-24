---
UID: NC:storport.HW_INTERRUPT
title: HW_INTERRUPT
author: windows-driver-content
description: The Storport driver calls the HwStorInterrupt routine after the HBA generates an interrupt request.
old-location: storage\hwstorinterrupt.htm
tech.root: storage
ms.assetid: 3c61d947-3e05-4750-a50c-be9b2dc573f0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_INTERRUPT, HwStorInterrupt, HwStorInterrupt routine [Storage Devices], storage.hwstorinterrupt, stormini_17f68641-1cfd-47b3-a52f-be98f96e693f.xml, storport/HwStorInterrupt
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
req.irql: DIRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_INTERRUPT callback function


## -description


The Storport driver calls the <b>HwStorInterrupt</b> routine after the HBA generates an interrupt request.


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area. 


## -returns



If the miniport driver finds that its HBA did not generate the interrupt, <b>HwStorInterrupt</b> should return <b>FALSE</b> as soon as possible. The <b>HwStorInterrupt</b> routine should return within 50 microseconds.




## -remarks



The name <b>HwStorInterrupt</b> is just a placeholder. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<pre class="syntax" xml:space="preserve"><code>typedef
BOOLEAN
HW_INTERRUPT (
  IN PVOID  DeviceExtension
  );</code></pre>
The <b>HwStorInterrupt</b> routine should return within 50 microseconds, ideally as short a time as possible. Therefore, all activity does not have to occur at high IRQL should be deferred to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557383">HwStorDpcRoutine</a> that is defined in the miniport driver and issued by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff567116">StorPortIssueDpc</a>.  The latency of the DPC is very low, and it will be called immediately after the return from high IRQL.

The port driver calls the <b>HwStorInterrupt</b> routine at DIRQL.


#### Examples

To define an <b>HwStorInterrupt</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorInterrupt</b> callback routine that is named <i>MyHwInterrupt</i>, use the <b>HW_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_INTERRUPT MyHwInterrupt;</pre>
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
MyHwInterrupt (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_INTERRUPT</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_INTERRUPT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557383">HwStorDpcRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567116">StorPortIssueDpc</a>
 

 

