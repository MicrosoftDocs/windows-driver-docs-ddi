---
UID: NC:storport.HW_STATE_CHANGE
title: HW_STATE_CHANGE
author: windows-driver-content
description: A miniport-provided callback that is called after a notification from StorPortStateChangeDetected is processed.
old-location: storage\hwstorstatechange.htm
old-project: storage
ms.assetid: E7E5E26A-B477-453C-AAFC-9B3572F4FC72
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HW_STATE_CHANGE, HwStorStateChange, HwStorStateChange routine [Storage Devices], storage.hwstorstatechange, storport/HwStorStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: DISPATCH
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	storport.h
api_name:
-	HwStorStateChange
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_STATE_CHANGE callback


## -description


A miniport-provided callback that is called  after a notification from <a href="..\storport\nf-storport-storportstatechangedetected.md"> StorPortStateChangeDetected</a> is processed.


## -prototype


````
HW_STATE_CHANGE HwStorStateChange;

VOID HwStorStateChange(
  _In_     IN PVOID DeviceExtension,
  _In_opt_ PVOID    Context,
  _In_     SHORT    AddressType,
  _In_     PVOID    Address,
  _In_     ULONG    Status
)
{ ... }
````


## -parameters




### -param HwDeviceExtension


### -param Context [in, optional]

The context supplied as <i>HwStateChangeContext</i> by the miniport in the call to <a href="..\storport\nf-storport-storportstatechangedetected.md"> StorPortStateChangeDetected</a>.


### -param AddressType [in]

The type of the address in <i>Address</i>.


### -param Address [in]

A pointer to a <a href="..\minitape\ns-minitape-_stor_address.md">STOR_ADDRESS</a> structure for the entity whose state change was processed.


### -param Status [in]

The processing status for the state change notification.


#### - DeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


## -returns



None.




## -remarks



The <i>HwStorStateChange</i> is called with the StartIo lock acquired by Storport.

This callback enables miniports to do any additional processing that is needed after hardware addition or removal. If a hardware change occurs on the HBA port or bus, the miniport can call <a href="..\storport\nf-storport-storportstatechangedetected.md"> StorPortStateChangeDetected</a> to alert the system of the event.

If the value for <i>Status</i> is  &lt; 0x80000000, then the notification processing was successful. Otherwise, the notification process failed.

The name <i>HwStorStateChange</i> is just a placeholder for the miniport function that is pointed to by the <i>HwStateChange</i> parameter of  <a href="..\storport\nf-storport-storportstatechangedetected.md"> StorPortStateChangeDetected</a>. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_STATE_CHANGE (
    _In_ PVOID HwDeviceExtension,
    _In_opt_ PVOID Context,
    _In_ SHORT AddressType,
    _In_ PVOID Address,
    _In_ ULONG Status
    );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\storport\nf-storport-storportstatechangedetected.md"> StorPortStateChangeDetected</a>



<a href="..\minitape\ns-minitape-_stor_address.md">STOR_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_STATE_CHANGE routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

