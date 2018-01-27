---
UID: NC:storport.HW_COMPLETE_SERVICE_IRP
title: HW_COMPLETE_SERVICE_IRP
author: windows-driver-content
description: The HwStorCompleteServiceIrp routine is called when the virtual adapter is being removed. When this happens, the Storport virtual miniport can complete any reverse-callback IRPs received in HwStorCompleteServiceIrp.
old-location: storage\hwstorcompleteserviceirp.htm
old-project: storage
ms.assetid: 1a6a6073-27ec-43c0-b5ec-37ef4177fa54
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorcompleteserviceirp, HwStorCompleteServiceIrp routine [Storage Devices], HwStorCompleteServiceIrp, HW_COMPLETE_SERVICE_IRP, HW_COMPLETE_SERVICE_IRP, storport/HwStorCompleteServiceIrp, storvmini_57cddd18-134c-4ecc-9180-4c4b3ff3903d.xml
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
req.typenames: *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
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
</table></span></div>The port driver calls the Storport virtual miniport driver's <b>HwStorCompleteServiceIrp</b>routine at PASSIVE_LEVEL without holding any spin locks. The virtual miniport driver completes the IRP by calling the <b>HwStorCompleteServiceIrp</b> routine.



## -see-also

<a href="..\storport\nf-storport-storportcompleteserviceirp.md">StorPortCompleteServiceIrp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorCompleteServiceIrp routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

