---
UID: NC:storport.HW_FREE_ADAPTER_RESOURCES
title: HW_FREE_ADAPTER_RESOURCES
author: windows-driver-content
description: The HwStorFreeAdapterResources callback routine allows the Storport virtual miniport driver to free resources when the virtual adapter is being removed. This is the last callback routine for the adapter.
old-location: storage\hwstorfreeadapterresources.htm
tech.root: storage
ms.assetid: 2f12aab4-ca6e-473b-a342-2881c4a7b133
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_FREE_ADAPTER_RESOURCES, HwStorFreeAdapterResources, HwStorFreeAdapterResources routine [Storage Devices], storage.hwstorfreeadapterresources, storport/HwStorFreeAdapterResources, storvmini_88adb6fa-10a8-4ee7-90d3-881564ed5cfd.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorFreeAdapterResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_FREE_ADAPTER_RESOURCES callback function


## -description


The <b>HwStorFreeAdapterResources</b> callback routine allows the Storport virtual miniport driver to free resources when the virtual adapter is being removed. This is the last callback routine for the adapter.


## -parameters




### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.


## -returns



None




## -remarks



The name <b>HwStorFreeAdapterResources</b> is  placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PHW_FREE_ADAPTER_RESOURCES) (
  IN PVOID  DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport's <b>HwStorFreeAdapterResources</b> at PASSIVE_LEVEL. 


#### Examples

To define an <b>HwStorFreeAdapterResources</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorBuildIo</b><b>HwStorFreeAdapterResources</b>callback routine that is named <i>MyHwAdapterFreeResources</i>, use the <b>HW_FREE_ADAPTER_RESOURCES</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_FREE_ADAPTER_RESOURCES MyHwAdapterFreeResources;</pre>
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
MyHwAdapterFreeResources (
  _In_ PVOID  DeviceExtension
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_FREE_ADAPTER_RESOURCES</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_FREE_ADAPTER_RESOURCES</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.



