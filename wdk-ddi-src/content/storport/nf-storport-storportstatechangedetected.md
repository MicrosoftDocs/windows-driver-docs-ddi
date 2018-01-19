---
UID: NF:storport.StorPortStateChangeDetected
title: StorPortStateChangeDetected function
author: windows-driver-content
description: Notifies the Storport port driver of a state change for a logical unit number (LUN), host bus adapter (HBA) port, or target device.
old-location: storage\storportstatechangedetected.htm
old-project: storage
ms.assetid: 3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortStateChangeDetected
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortStateChangeDetected
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortStateChangeDetected function



## -description
Notifies the Storport port driver of a state change for a logical unit number (LUN), host bus adapter (HBA) port, or target device.



## -syntax

````
ULONG StorPortStateChangeDetected(
  _In_     PVOID            HwDeviceExtension,
  _In_     ULONG            ChangedEntity,
  _In_     PSTOR_ADDRESS    Address,
  _In_     ULONG            Attributes,
  _In_opt_ PHW_STATE_CHANGE HwStateChange,
  _In_opt_ ULONG            HwStateChangeContext
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param ChangedEntity [in]

Flags indicating the entities whose state has changed. This is a bitwise <b>OR</b> combination of these values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param STATE_CHANGE_LUN
### -param 1 (0x1)

</td>
<td width="60%">
LUN state has changed.

</td>
</tr>
<tr>

### -param STATE_CHANGE_TARGET
### -param 2 (0x2)

</td>
<td width="60%">
Target state has changed.

</td>
</tr>
<tr>

### -param STATE_CHANGE_BUS
### -param 4 (0x4)

</td>
<td width="60%">
 Bus or port state has changed.

</td>
</tr>
</table>
 


### -param Address [in]

The address of the entity with the state change. <i>Address</i> value cannot change until the callback at  <i>HwStateChange</i> is invoked. If <i>Address</i> is allocated in memory, the memory should be freed by the callback routine.


### -param Attributes [in]

Attributes associated with the entity. These are a bitwise <b>OR</b> combination of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param ATTRIBUTE_VM_PASSTHROUGH_LUN

</td>
<td width="60%">
LUNs are reserved for virtual machine use.

</td>
</tr>
</table>
 


### -param HwStateChange [in, optional]

A pointer to a callback routine supplied by the miniport. If present, the Storport driver will call this routine when the driver is finished processing this state change notification.


### -param HwStateChangeContext [in, optional]

A miniport-supplied context value that is included when the routine set in <i>HwStateChange</i> is called.


## -returns
A status value indicating the result of the notification. This can be one of these values:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The state change notification is scheduled for processing.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The address type or the entity type is invalid.
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>A prior notification is in process and this one cannot be scheduled.

 


## -remarks
A successful call to<b> StorPortStateChangeDetected</b> results in re-enumeration of the changed entity. 

Only one state change request can be active at any time. If a miniport needs to make another <b> StorPortStateChangeDetected</b> call, it should provide a <i>HwStateChange</i> callback and make another call to <b> StorPortStateChangeDetected</b> after the callback to <i>HwStateChange</i> occurs. If a miniport wants to indicate multiple state changes at the same time, the miniport can call <b> StorPortStateChangeDetected</b> once, with  changed entities set in <i>ChangedEntity</i> that includes all of the current state changes.

If multiple flags are specified in <i>ChangedEntity</i>, the  flag with greater value will have precedence over lesser ones.


## -see-also
<dl>
<dt>
<a href="..\storport\nc-storport-hw_state_change.md">HwStorStateChange</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortStateChangeDetected routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

