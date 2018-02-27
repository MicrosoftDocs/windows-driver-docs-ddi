---
UID: NF:ks.KsForwardAndCatchIrp
title: KsForwardAndCatchIrp function
author: windows-driver-content
description: The KsForwardAndCatchIrp function forwards an IRP to the specified driver after initializing the next stack location, and regains control of the IRP on completion from that driver.
old-location: stream\ksforwardandcatchirp.htm
old-project: stream
ms.assetid: 87a873c2-07d3-4f76-bc26-5fcae4b960e7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsForwardAndCatchIrp, KsForwardAndCatchIrp function [Streaming Media Devices], ks/KsForwardAndCatchIrp, ksfunc_db5ae1e5-b0c8-4703-866f-a3f060e5ffb3.xml, stream.ksforwardandcatchirp
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsForwardAndCatchIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsForwardAndCatchIrp function


## -description


The <b>KsForwardAndCatchIrp</b> function forwards an IRP to the specified driver after initializing the next stack location, and regains control of the IRP on completion from that driver. The function is used with devices that can be stacked and do not use file objects to communicate.

If a file object is being used, the caller must initialize the current stack location with that file object before calling the <b>KsForwardAndCatchIrp</b> function. The function verifies that there is a new stack location to copy into before attempting to do so. If there is not a new stack location, the function returns STATUS_INVALID_DEVICE_REQUEST. Regardless of whether a new stack location is present, the IRP is not completed.


## -syntax


````
NTSTATUS KsForwardAndCatchIrp(
  _In_ PDEVICE_OBJECT DeviceObject ,
  _In_ PIRP           Irp ,
  _In_ PFILE_OBJECT   FileObject ,
  _In_ KSSTACK_USE    StackUse 
);
````


## -parameters




### -param DeviceObject [in]

Specifies the device to forward the IRP to.


### -param Irp [in]

Specifies the IRP that is being forwarded to the specified driver.


### -param FileObject [in]

Specifies a file object value to copy to the next stack location. This can be <b>NULL</b> in order to set no file object, but the value is always copied to the next stack location. If the current file object is to be preserved, it must be passed in this parameter. 


### -param StackUse [in]

Specifies a value enumerated by KSSTACK_USE. If the value is <i>KsStackCopyToNewLocation</i>, the parameters are copied to the next stack location. If the value is <i>KsStackReuseCurrentLocation</i>, the current stack location is reused when the IRP is forwarded and the stack location is returned to the current location. If the value is <i>KsStackUseNewLocation</i>, the new stack location is used as is.


## -returns



The <b>KsForwardAndCatchIrp</b> function returns the result of the <b>IoCallDriver</b>, or it returns an invalid status if no more stack depth is available.




## -remarks



The type KSSTACK_USE enumeration specifies how the IRP stack is used when forwarding the IRP to the next driver.

<table>
<tr>
<th>Enumeration</th>
<th>Description</th>
</tr>
<tr>
<td>
KsStackCopyToNewLocation

</td>
<td>
Indicates that the parameters are to be copied to the next stack location.

</td>
</tr>
<tr>
<td>
KsStackReuseCurrentLocation

</td>
<td>
Indicates that the current stack location is to be reused.

</td>
</tr>
<tr>
<td>
KsStackUseNewLocation

</td>
<td>
Indicates that the next stack location is to be used without modification.

</td>
</tr>
</table>
 



