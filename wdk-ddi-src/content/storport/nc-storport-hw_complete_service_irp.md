---
UID: NC:storport.HW_COMPLETE_SERVICE_IRP
title: HW_COMPLETE_SERVICE_IRP
author: windows-driver-content
description: The HwStorCompleteServiceIrp routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in HwStorCompleteServiceIrp.
old-location: storage\hwstorcompleteserviceirp.htm
old-project: storage
ms.assetid: 1a6a6073-27ec-43c0-b5ec-37ef4177fa54
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HW_COMPLETE_SERVICE_IRP, HwStorCompleteServiceIrp, HwStorCompleteServiceIrp routine [Storage Devices], storage.hwstorcompleteserviceirp, storport/HwStorCompleteServiceIrp, storvmini_57cddd18-134c-4ecc-9180-4c4b3ff3903d.xml
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorCompleteServiceIrp
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_COMPLETE_SERVICE_IRP callback


## -description


The <b>HwStorCompleteServiceIrp</b> routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in <b>HwStorCompleteServiceIrp</b>.


## -prototype


````
HW_COMPLETE_SERVICE_IRP HwStorCompleteServiceIrp;

VOID HwStorCompleteServiceIrp(
   IN PVOID DeviceExtension
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.


## -returns



None




## -remarks



The name <b>HwStorCompleteServiceIrp</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_COMPLETE_SERVICE_IRP (
  _In_ PVOID  DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport driver's <b>HwStorCompleteServiceIrp</b>routine at PASSIVE_LEVEL without holding any spin locks. The virtual miniport driver completes the IRP by calling the <b>HwStorCompleteServiceIrp</b> routine.


#### Examples

To define an <b>HwStorCompleteServiceIrp</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorCompleteServiceIrp</b> callback routine that is named <i>MyHwCompleteServiceIrp</i>, use the <b>HW_COMPLETE_SERVICE_IRP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_COMPLETE_SERVICE_IRP MyHwCompleteServiceIrp;</pre>
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
MyHwCompleteServiceIrp (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_COMPLETE_SERVICE_IRP</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_COMPLETE_SERVICE_IRP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorCompleteServiceIrp routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

