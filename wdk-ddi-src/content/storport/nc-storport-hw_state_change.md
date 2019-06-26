---
UID: NC:storport.HW_STATE_CHANGE
title: HW_STATE_CHANGE (storport.h)
description: A miniport-provided callback that is called after a notification from StorPortStateChangeDetected is processed.
old-location: storage\hwstorstatechange.htm
tech.root: storage
ms.assetid: E7E5E26A-B477-453C-AAFC-9B3572F4FC72
ms.date: 03/29/2018
ms.keywords: HW_STATE_CHANGE, HwStorStateChange, HwStorStateChange routine [Storage Devices], storage.hwstorstatechange, storport/HwStorStateChange
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- storport.h
api_name:
- HwStorStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_STATE_CHANGE callback function


## -description


A miniport-provided callback that is called  after a notification from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportstatechangedetected"> StorPortStateChangeDetected</a> is processed.


## -parameters




### -param HwDeviceExtension


### -param Context [in, optional]

The context supplied as <i>HwStateChangeContext</i> by the miniport in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportstatechangedetected"> StorPortStateChangeDetected</a>.


### -param AddressType [in]

The type of the address in <i>Address</i>.


### -param Address [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a> structure for the entity whose state change was processed.


### -param Status [in]

The processing status for the state change notification.


#### - DeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


## -returns



None.




## -remarks



The <i>HwStorStateChange</i> is called with the StartIo lock acquired by Storport.

This callback enables miniports to do any additional processing that is needed after hardware addition or removal. If a hardware change occurs on the HBA port or bus, the miniport can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportstatechangedetected"> StorPortStateChangeDetected</a> to alert the system of the event.

If the value for <i>Status</i> is  < 0x80000000, then the notification processing was successful. Otherwise, the notification process failed.

The name <i>HwStorStateChange</i> is just a placeholder for the miniport function that is pointed to by the <i>HwStateChange</i> parameter of  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportstatechangedetected"> StorPortStateChangeDetected</a>. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsi/ns-scsi-_stor_address">STOR_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportstatechangedetected"> StorPortStateChangeDetected</a>
 

 

