---
UID: NE:spbcx._SPB_REQUEST_TYPE
title: _SPB_REQUEST_TYPE (spbcx.h)
description: The SPB_REQUEST_TYPE enumeration specifies the type of SPB operation that a client is requesting.
old-location: spb\spb_request_type.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["SPB_REQUEST_TYPE enumeration"]
ms.keywords: "*PSPB_REQUEST_TYPE, SPB.spb_request_type, SPB_REQUEST_TYPE, SPB_REQUEST_TYPE enumeration [Buses], SpbRequestTypeLockConnection, SpbRequestTypeLockController, SpbRequestTypeMax, SpbRequestTypeOther, SpbRequestTypeRead, SpbRequestTypeSequence, SpbRequestTypeUndefined, SpbRequestTypeUnlockConnection, SpbRequestTypeUnlockController, SpbRequestTypeWrite, _SPB_REQUEST_TYPE, spbcx/SPB_REQUEST_TYPE, spbcx/SpbRequestTypeLockConnection, spbcx/SpbRequestTypeLockController, spbcx/SpbRequestTypeMax, spbcx/SpbRequestTypeOther, spbcx/SpbRequestTypeRead, spbcx/SpbRequestTypeSequence, spbcx/SpbRequestTypeUndefined, spbcx/SpbRequestTypeUnlockConnection, spbcx/SpbRequestTypeUnlockController, spbcx/SpbRequestTypeWrite"
req.header: spbcx.h
req.include-header: Spb.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
f1_keywords:
 - _SPB_REQUEST_TYPE
 - spbcx/_SPB_REQUEST_TYPE
 - PSPB_REQUEST_TYPE
 - spbcx/PSPB_REQUEST_TYPE
 - SPB_REQUEST_TYPE
 - spbcx/SPB_REQUEST_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - spbcx.h
api_name:
 - _SPB_REQUEST_TYPE
 - PSPB_REQUEST_TYPE
 - SPB_REQUEST_TYPE
---

# _SPB_REQUEST_TYPE enumeration

## -description

The **SPB_REQUEST_TYPE** enumeration specifies the type of SPB operation that a client is requesting.

## -enum-fields

### -field SpbRequestTypeUndefined

For internal use only.

### -field SpbRequestTypeRead

 A read operation. The transfer direction for read data is from the target device to the client (peripheral driver). Your SPB controller driver will see requests of this type only if it registers an [EvtSpbControllerIoRead](./nc-spbcx-evt_spb_controller_read.md) callback function.

### -field SpbRequestTypeWrite

A write operation. The transfer direction for write data is from the client to the target device. Your SPB controller driver receives requests of this type only if it registers an [EvtSpbControllerIoWrite](./nc-spbcx-evt_spb_controller_write.md) callback function.

### -field SpbRequestTypeSequence

A sequence of transfer (read and write) operations combined into a single request. Your SPB controller driver receives requests of this type only if it registers an [EvtSpbControllerIoSequence](./nc-spbcx-evt_spb_controller_sequence.md) callback function. Otherwise, the SPB framework extension (SpbCx) will convert an I/O transfer sequence into a series of I/O requests of type **SpbRequestTypeRead** and **SpbRequestTypeWrite**, and send these requests to the SPB controller driver's *EvtSpbControllerIoRead* and *EvtSpbControllerIoWrite* callback functions.

### -field SpbRequestTypeLockController

A request to lock the controller exclusively for bus transfers to or from the specified target device. Your SPB controller driver receives requests of this type only if it registers an [EvtSpbControllerLock](./nc-spbcx-evt_spb_controller_lock.md) callback function.

### -field SpbRequestTypeUnlockController

A request to unlock the controller for the specified target device. Your SPB controller driver receives requests of this type through its [EvtSpbControllerUnlock](./nc-spbcx-evt_spb_controller_unlock.md) callback function.

### -field SpbRequestTypeLockConnection

A request to lock the specified target device for exclusive use by a client. This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see [IOCTL_SPB_LOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_connection-control-code).

### -field SpbRequestTypeUnlockConnection

A request to unlock the specified target device. This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see [IOCTL_SPB_UNLOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_connection-control-code).

### -field SpbRequestTypeOther

An unknown I/O control (IOCTL) request sent by a client (peripheral driver) to a target device on the bus. Call the [WdfRequestGetParameters](../wdfrequest/nf-wdfrequest-wdfrequestgetparameters.md) method to retrieve the parameters for this request; for this call, use the SPBREQUEST handle for the *Request* parameter. Your SPB controller driver receives requests of this type only if it registers an [EvtSpbControllerIoOther](./nc-spbcx-evt_spb_controller_other.md) callback function. Otherwise, SpbCx rejects unknown IOCTL requests.

### -field SpbRequestTypeMax

For internal use only.

## -remarks

The [SPB_REQUEST_PARAMETERS](/previous-versions/hh406209(v=vs.85)) structure contains an **SPB_REQUEST_TYPE** enumeration value.

## -see-also

* [EvtSpbControllerIoOther](./nc-spbcx-evt_spb_controller_other.md)
* [EvtSpbControllerIoRead](./nc-spbcx-evt_spb_controller_read.md)
* [EvtSpbControllerIoSequence](./nc-spbcx-evt_spb_controller_sequence.md)
* [EvtSpbControllerIoWrite](./nc-spbcx-evt_spb_controller_write.md)
* [EvtSpbControllerLock](./nc-spbcx-evt_spb_controller_lock.md)
* [EvtSpbControllerUnlock](./nc-spbcx-evt_spb_controller_unlock.md)
* [IOCTL_SPB_LOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_connection-control-code)
* [IOCTL_SPB_UNLOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_connection-control-code)
* [SPB_REQUEST_PARAMETERS](/previous-versions/hh406209(v=vs.85))
* [WdfRequestGetParameters](../wdfrequest/nf-wdfrequest-wdfrequestgetparameters.md)