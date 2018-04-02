---
UID: NF:ks.KsAllocateDeviceHeader
title: KsAllocateDeviceHeader function
author: windows-driver-content
description: The KsAllocateDeviceHeader function allocates and initializes the required device extension header.
old-location: stream\ksallocatedeviceheader.htm
old-project: stream
ms.assetid: 554f03bf-cacd-401b-aa34-fcfe1c31091e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAllocateDeviceHeader, KsAllocateDeviceHeader function [Streaming Media Devices], ks/KsAllocateDeviceHeader, ksfunc_715031de-7d7e-4e24-8e1c-072c7bc271fb.xml, stream.ksallocatedeviceheader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAllocateDeviceHeader
product: Windows
targetos: Windows
req.typenames: 
---

# KsAllocateDeviceHeader function


## -description


The <b>KsAllocateDeviceHeader</b> function allocates and initializes the required device extension header. 


## -parameters




### -param Header [out]

Points to the location in which to return a pointer to the initialized header.


### -param ItemsCount [in]

Specifies the number of subitems in the <i>ItemsList</i>. This should be zero if an <i>ItemsList</i> is not passed.


### -param ItemsList [in, optional]

Optional. Points to a KSOBJECT_CREATE_ITEM structure for each subitem. If there are no subitems, this value should be <b>NULL</b> and <i>ItemsCount</i> should be zero.


## -returns



The <b>KsAllocateDeviceHeader</b> function returns STATUS_SUCCESS if successful or STATUS_INSUFFICIENT_RESOURCES if unable to allocate the necessary resources.




## -remarks



The <b>KsAllocateDeviceHeader</b> function allocates memory for the KSDEVICE_HEADER structure for a device. When the header is no longer needed, the driver should call the <b>KsFreeDeviceHeader</b> function to free the memory allocated.

If subobjects exist for a given device, the driver must, before calling <b>KsAllocateDeviceHeader</b>, allocate a buffer of either paged or nonpaged memory of sufficient size to hold a KSOBJECT_CREATE_ITEM structure for each subobject. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>/* Allocate a buffer for 4 subobjects for a given streaming device */
PKSOBJECT_CREATE_ITEM createBuffer ;
ULONG bufferSize  = (sizeof (KSOBJECT_CREATE_ITEM)) * 4 ;
 
createBuffer = (PKSOBJECT_CREATE_ITEM)
               ExAllocatePoolWithTag (PagedPool, bufferSize) ;
 </pre>
</td>
</tr>
</table></span></div>
Drivers must not free the memory allocated for the subobject KSOBJECT_CREATE_ITEM list until after calling <b>KsFreeDeviceHeader</b>. Failure to do so can result in a bug check condition. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562560">KsFreeDeviceHeader</a>
 

 

