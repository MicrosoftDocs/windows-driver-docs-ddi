---
UID: NF:vhf.VhfDelete
title: VhfDelete function
author: windows-driver-content
description: The HID Source device driver calls this method to delete a VHF device.
old-location: hid\vhfdelete.htm
old-project: hid
ms.assetid: 85252A53-E653-4D14-B1FE-72CA9AFA1F10
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VhfDelete, VhfDelete method [Human Input Devices], hid.vhfdelete, vhf/VhfDelete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vhf.h
req.include-header: 
req.target-type: Windows
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
req.lib: VhfKm.lib
req.dll: 
req.irql: If Wait is TRUE, PASSIVE_LEVEL; if Wait is FALSE <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	vhfKm.lib
-	vhfKm.dll
api_name:
-	VhfDelete
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# VhfDelete function


## -description


The HID Source device driver calls this method to delete a VHF device.


## -syntax


````
void VhfDelete(
  [in] VHFHANDLE VhfHandle,
  [in] BOOLEAN   Wait
);
````


## -parameters




### -param VhfHandle [in]

A handle to a virtual HID device that your HID source driver received in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>.


### -param Wait [in]

TRUE to return synchronously after deleting a device. In this case, Virtual HID Framework (VHF) does not return until the device is reported as missing to PnP Manager and <a href="..\vhf\nc-vhf-evt_vhf_cleanup.md">EvtVhfCleanup</a> callback function returns. 

FALSE to return asynchronously. See Remarks for more information.


## -returns



This method does not return a value.




## -remarks



The HID source driver must stop initiating new requests for the Virtual HID Framework (VHF) just before calling <b>VhfDelete</b>. <b>VhfDelete</b> can be called synchronously or asynchronously.   

To call <b>VhfDelete</b> synchronously,  call it at PASSIVE_LEVEL with the <i>Wait</i> parameter set to TRUE. In this case, it returns synchronously after completing the deletion. If the HID source driver has registered an <a href="..\vhf\nc-vhf-evt_vhf_cleanup.md">EvtVhfCleanup</a> callback function with VHF, it invokes that callback before <b>VhfDelete</b> returns. The function might be invoked on the same thread.

To call <b>VhfDelete</b> asynchronously, call it at maximum DISPATCH_LEVEL. If you call it at DISPATCH_LEVEL, then <i>Wait</i> parameter must be set to FALSE, the function returns immediately. VHF invokes the <a href="..\vhf\nc-vhf-evt_vhf_cleanup.md">EvtVhfCleanup</a> callback at a later time after the deletion has completed. 

There are no restrictions on when a KMDF driver should call this function. It is recommended to call it from a function matching the <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> call. For example, if <b>VhfCreate</b> is called from <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>, then call <b>VhfDelete</b> synchronously from <i>EvtDeviceCleanupCallback</i>.




## -see-also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20VhfDelete method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

