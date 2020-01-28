---
UID: NE:usbfnbase._USBFN_EVENT
title: _USBFN_EVENT (usbfnbase.h)
description: Defines notifications sent to class drivers.
old-location: buses\usbfn_event.htm
tech.root: usbref
ms.assetid: 4A1A4E49-6452-4291-8CD4-FA390C1F167E
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_EVENT, USBFN_EVENT, USBFN_EVENT enumeration [Buses], UsbfnEventAttach, UsbfnEventBusTearDown, UsbfnEventConfigured, UsbfnEventDetach, UsbfnEventMaximum, UsbfnEventMinimum, UsbfnEventPortType, UsbfnEventReset, UsbfnEventResume, UsbfnEventSetInterface, UsbfnEventSetupPacket, UsbfnEventSuspend, UsbfnEventUnConfigured, _USBFN_EVENT, buses.usbfn_event, usbfnbase/USBFN_EVENT, usbfnbase/UsbfnEventAttach, usbfnbase/UsbfnEventBusTearDown, usbfnbase/UsbfnEventConfigured, usbfnbase/UsbfnEventDetach, usbfnbase/UsbfnEventMaximum, usbfnbase/UsbfnEventMinimum, usbfnbase/UsbfnEventPortType, usbfnbase/UsbfnEventReset, usbfnbase/UsbfnEventResume, usbfnbase/UsbfnEventSetInterface, usbfnbase/UsbfnEventSetupPacket, usbfnbase/UsbfnEventSuspend, usbfnbase/UsbfnEventUnConfigured"
f1_keywords:
 - "usbfnbase/USBFN_EVENT"
req.header: usbfnbase.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbfnbase.h
api_name:
- USBFN_EVENT
product:
- Windows
targetos: Windows
req.typenames: USBFN_EVENT, *PUSBFN_EVENT
---

# _USBFN_EVENT enumeration


## -description


Defines notifications sent to class drivers.


## -enum-fields




### -field UsbfnEventMinimum

The minimum value in this enumeration.


### -field UsbfnEventAttach

VBUS is powered. No action is required.


### -field UsbfnEventReset

USBFN has completed a USB Reset. If previously configured, class drivers should reset their state. Transfer requests will be cancelled.


### -field UsbfnEventDetach

    VBUS is no longer powered.
    If previously configured, class drivers should
    reset their state. Transfer requests will be cancelled.
    The <b>BusSpeed</b> field of the notification is set appropriately.


### -field UsbfnEventSuspend

    There have been no SOF packets on the bus for 3ms.
    If a class driver wants to issue a remote wake up,
     the driver must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_signal_remote_wakeup">IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_in">IOCTL_INTERNAL_USBFN_TRANSFER_IN</a>.


### -field UsbfnEventResume

USBFN has resumed from suspend to the previous state.


### -field UsbfnEventSetupPacket

    USBFN has received a setup packet with
    <b>bmRequestType.Type</b> set to BMREQUEST_CLASS and
    <b>bmRequestType.Recipient</b> set to BMREQUEST_TO_INTERFACE.
    USBFN forwarded the setup packet to the class driver
    specified in <b>wIndex.LowByte</b>.

 The setup packet is available in the <b>SetupPacket</b> field of the
    event. If the control transfer does not require a data stage,
     class drivers should respond with
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_out">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT</a>.
    If a data stage is required, class drivers should respond with
    one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_in">IOCTL_INTERNAL_USBFN_TRANSFER_IN</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_out">IOCTL_INTERNAL_USBFN_TRANSFER_OUT</a>, followed by
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_in">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN</a> or <b>IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT</b> in the opposite
    direction.


### -field UsbfnEventConfigured

    USBFN has received a SET_CONFIGURATION setup packet. Transfer
    requests from class drivers are now permitted.
    The <b>ConfigurationValue</b> of the notification is set to <b>wValue.W</b>.


### -field UsbfnEventUnConfigured

    USBFN has received a SET_CONFIGURATION setup packet with
    <b>wValue.W</b> set to 0. If previously configured, class drivers should
    reset their state. Transfer requests will be cancelled.


### -field UsbfnEventPortType

Deprecated.


### -field UsbfnEventBusTearDown

Deprecated.


### -field UsbfnEventSetInterface

USBFN has received a SET_INTERFACE setup packet.  On receiving this
    notification the class driver should query for the new endpoint set
    for the interface.


### -field UsbfnEventMaximum

The minimum value in this enumeration.

