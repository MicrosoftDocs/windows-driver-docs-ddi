---
UID: NC:storport.HW_PASSIVE_INITIALIZE_ROUTINE
title: HW_PASSIVE_INITIALIZE_ROUTINE
author: windows-driver-content
description: The HwStorPassiveInitializeRoutine callback routine is called after the HwStorInitialize routine when the current IRQL is at PASSIVE_LEVEL.
old-location: storage\hwstorpassiveinitializeroutine.htm
tech.root: storage
ms.assetid: 70f65a4e-0a98-4135-bb38-530c729538a3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_PASSIVE_INITIALIZE_ROUTINE, HwStorPassiveInitializeRoutine, HwStorPassiveInitializeRoutine routine [Storage Devices], storage.hwstorpassiveinitializeroutine, stormini_e2404f14-1cdc-44d7-bd58-97acfa57bc36.xml, storport/HwStorPassiveInitializeRoutine
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorPassiveInitializeRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_PASSIVE_INITIALIZE_ROUTINE callback function


## -description


The <b>HwStorPassiveInitializeRoutine</b> callback routine is called after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557396">HwStorInitialize</a> routine when the current IRQL is at PASSIVE_LEVEL. The <b>HwStorPassiveInitializeRoutine</b> callback is set by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567056">StorPortEnablePassiveInitialization</a> routine. Initializing of the miniport's deferred procedure calls (DPCs) occurs in the <b>HwStorPassiveInitializeRoutine</b> callback.


## -parameters




### -param DeviceExtension








#### - HwDeviceExtension

A pointer to a per-adapter storage area. 


## -returns



The <b>HwStorPassiveInitializeRoutine</b> routine returns <b>TRUE</b> if the miniport successfully initialized the processing of DPCs, or <b>FALSE</b> if the initialization process failed. 




## -remarks



The <b>HwStorPassiveInitializeRoutine</b> routine should initialize any DPCs that the miniport driver will use. The port driver calls <b>HwStorPassiveInitializeRoutine</b> at PASSIVE_LEVEL without any spin locks held. Interrupts are enabled while this routine is called.

The name <b>HwStorPassiveInitializeRoutine</b> is just a placeholder. The actual prototype for this callback routine is defined in <i>storport.h</i>as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
(*PHW_PASSIVE_INITIALIZE_ROUTINE) (
  _In_ PVOID DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the <b>HwStorPassiveInitializeRoutine</b> routine at PASSIVE IRQL without acquiring any spin locks.


#### Examples

To define an <b>HwStorPassiveInitializeRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorPassiveInitializeRoutine</b> callback routine that is named <i>MyHwPassiveInitialize</i>, use the <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_PASSIVE_INITIALIZE_ROUTINE MyHwPassiveInitialize;</pre>
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
MyHwPassiveInitialize (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567056">StorPortEnablePassiveInitialization</a>
 

 

