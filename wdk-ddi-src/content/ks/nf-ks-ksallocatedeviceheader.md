---
UID: NF:ks.KsAllocateDeviceHeader
title: KsAllocateDeviceHeader function
author: windows-driver-content
description: The KsAllocateDeviceHeader function allocates and initializes the required device extension header.
old-location: stream\ksallocatedeviceheader.htm
old-project: stream
ms.assetid: 554f03bf-cacd-401b-aa34-fcfe1c31091e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KsAllocateDeviceHeader, stream.ksallocatedeviceheader, KsAllocateDeviceHeader function [Streaming Media Devices], KsAllocateDeviceHeader, ksfunc_715031de-7d7e-4e24-8e1c-072c7bc271fb.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsAllocateDeviceHeader
product: Windows
targetos: Windows
req.typenames: 
---

# KsAllocateDeviceHeader function


## -description


The <b>KsAllocateDeviceHeader</b> function allocates and initializes the required device extension header. 


## -syntax


````
NTSTATUS KsAllocateDeviceHeader(
  _Out_    KSDEVICE_HEADER       *Header,
  _In_     ULONG                 ItemsCount,
  _In_opt_ PKSOBJECT_CREATE_ITEM ItemsList
);
````


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

<a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>



<a href="..\ks\nf-ks-ksfreedeviceheader.md">KsFreeDeviceHeader</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateDeviceHeader function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

