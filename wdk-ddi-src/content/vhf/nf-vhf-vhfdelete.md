---
UID: NF:vhf.VhfDelete
title: VhfDelete function (vhf.h)
description: The HID Source device driver calls this method to delete a VHF device.
old-location: hid\vhfdelete.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["VhfDelete function"]
ms.keywords: VhfDelete, VhfDelete method [Human Input Devices], hid.vhfdelete, vhf/VhfDelete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VhfDelete
 - vhf/VhfDelete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - vhfKm.lib
 - vhfKm.dll
api_name:
 - VhfDelete
---

# VhfDelete function


## -description

The HID Source device driver calls this method to delete a VHF device.

## -parameters

### -param VhfHandle 

[in]
A handle to a virtual HID device that your HID source driver received in the previous call to <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a>.

### -param Wait 

[in]
TRUE to return synchronously after deleting a device. In this case, Virtual HID Framework (VHF) does not return until the device is reported as missing to PnP Manager and <a href="/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_cleanup">EvtVhfCleanup</a> callback function returns. 

FALSE to return asynchronously. See Remarks for more information.

## -remarks

The HID source driver must stop initiating new requests for the Virtual HID Framework (VHF) just before calling <b>VhfDelete</b>. <b>VhfDelete</b> can be called synchronously or asynchronously.   

To call <b>VhfDelete</b> synchronously,  call it at PASSIVE_LEVEL with the <i>Wait</i> parameter set to TRUE. In this case, it returns synchronously after completing the deletion. If the HID source driver has registered an <a href="/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_cleanup">EvtVhfCleanup</a> callback function with VHF, it invokes that callback before <b>VhfDelete</b> returns. The function might be invoked on the same thread.

To call <b>VhfDelete</b> asynchronously, call it at maximum DISPATCH_LEVEL. If you call it at DISPATCH_LEVEL, then <i>Wait</i> parameter must be set to FALSE, the function returns immediately. VHF invokes the <a href="/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_cleanup">EvtVhfCleanup</a> callback at a later time after the deletion has completed. 

There are no restrictions on when a KMDF driver should call this function. It is recommended to call it from a function matching the <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a> call. For example, if <b>VhfCreate</b> is called from <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>, then call <b>VhfDelete</b> synchronously from <i>EvtDeviceCleanupCallback</i>.

## -see-also

<a href="/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>
