---
UID: NC:storport.HW_TIMER
title: HW_TIMER
description: The HwStorTimer routine is called after the interval that is specified when the miniport driver called StorPortNotification with the RequestTimerCall NotificationType value.
old-location: storage\hwstortimer.htm
tech.root: storage
ms.assetid: 61aced1b-9f8a-454a-901c-561ec6179873
ms.date: 03/29/2018
ms.keywords: HW_TIMER, HwStorTimer, HwStorTimer routine [Storage Devices], storage.hwstortimer, stormini_6127daf5-8672-4bf4-9241-b67bed14b8f8.xml, storport/HwStorTimer
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_TIMER callback function


## -description


The <b>HwStorTimer</b> routine is called after the interval that is specified when the miniport driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a> with the <b>RequestTimerCall</b><i> NotificationType</i> value.


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.


## -returns



None




## -remarks



The name <b>HwStorTimer</b> is only a placeholder. The actual prototype of this routine is defined in <i>Srb.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_TIMER (
  _In_ PVOID  DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>
If the miniport opts into multi-channel support, the StartIo spin lock is still taken. However, if the miniport has requested multiple channel support via PERF_CONFIGURATION_DATA, the StartIo spin lock is not taken or checked before the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> in the miniport.  This means that the <i>HwStorStartIo</i> callback  is not synchronized with the callback to the <i>HwStorTimer</i> routine when multi-channel support is used.  The miniport must do this on its own by using a compiler interlocked intrinsic, for example using <a href="https://msdn.microsoft.com/library/windows/hardware/ff547853">InterlockedCompareExchange</a>. 

A <b>HwStorTimer</b> routine is optional.


#### Examples

To define an <b>HwStorTimer</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorTimer</b> callback routine that is named <i>MyHwTimer</i>, use the <b>HW_TIMER</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_TIMER MyHwTimer;</pre>
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
VOID
MyHwTimer (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_TIMER</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_TIMER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a>
 

 

