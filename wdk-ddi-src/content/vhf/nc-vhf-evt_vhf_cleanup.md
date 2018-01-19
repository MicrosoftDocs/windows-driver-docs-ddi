---
UID: NC:vhf.EVT_VHF_CLEANUP
title: EVT_VHF_CLEANUP
author: windows-driver-content
description: The HID source driver implements this event callback to free resources that might the driver allocated to the virtual HID device.
old-location: hid\evtvhfcleanup.htm
old-project: hid
ms.assetid: 1D477E7B-E4EA-46E7-872C-3BEBFBD31702
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtVhfCleanup
req.alt-loc: vhf.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# EVT_VHF_CLEANUP callback



## -description
The HID source driver implements this event callback to free resources that might the driver allocated to the virtual HID device. 



## -prototype

````
EVT_VHF_CLEANUP EvtVhfCleanup;

void EvtVhfCleanup(
  _In_ PVOID  VhfClientContext
)
{ ... }
````


## -parameters

### -param VhfClientContext [in]

Pointer to the HID source driver-defined context structure that the driver passed in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> to create the virtual HID device.


## -returns
This callback function does not return a value.


## -remarks
To delete the virtual HID device, the HID source driver calls <a href="..\vhf\nf-vhf-vhfdelete.md">VhfDelete</a>. That call causes Virtual HID Framework (VHF) to invoke the previously-registered <i>EvtVhfCleanup</i>, if the callback function is  implemented by the HID source driver.  When the driver calls VhfDelete with <i>Wait</i> set to TRUE, <i>EvtVhfCleanup</i> gets called before <b>VhfDelete</b> returns. If <i>Wait</i> is FALSE, it might get called any time after <b>VhfDelete</b> is called that is before or after <b>VhfDelete</b> returns.

The call gives the HID source driver an opportunity to free resources allocated for the virtual HID device when that device is deleted. 

The HID source driver must not use the VHFHANDLE for the virtual HID device (created by <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>) after this callback function returns. Before invoking this callback function, VHF makes sure that there are no asynchronous operations pending.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20EVT_VHF_CLEANUP callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

