---
UID: NE:spbcx._SPB_REQUEST_TYPE
title: _SPB_REQUEST_TYPE (spbcx.h)
description: The SPB_REQUEST_TYPE enumeration specifies the type of SPB operation that a client is requesting.
old-location: spb\spb_request_type.htm
tech.root: SPB
ms.assetid: B3C2505E-A2B6-4D79-B8B7-9D1B53AA5B56
ms.date: 04/30/2018
keywords: ["_SPB_REQUEST_TYPE enumeration"]
ms.keywords: "*PSPB_REQUEST_TYPE, SPB.spb_request_type, SPB_REQUEST_TYPE, SPB_REQUEST_TYPE enumeration [Buses], SpbRequestTypeLockConnection, SpbRequestTypeLockController, SpbRequestTypeMax, SpbRequestTypeOther, SpbRequestTypeRead, SpbRequestTypeSequence, SpbRequestTypeUndefined, SpbRequestTypeUnlockConnection, SpbRequestTypeUnlockController, SpbRequestTypeWrite, _SPB_REQUEST_TYPE, spbcx/SPB_REQUEST_TYPE, spbcx/SpbRequestTypeLockConnection, spbcx/SpbRequestTypeLockController, spbcx/SpbRequestTypeMax, spbcx/SpbRequestTypeOther, spbcx/SpbRequestTypeRead, spbcx/SpbRequestTypeSequence, spbcx/SpbRequestTypeUndefined, spbcx/SpbRequestTypeUnlockConnection, spbcx/SpbRequestTypeUnlockController, spbcx/SpbRequestTypeWrite"
f1_keywords:
 - "spbcx/SPB_REQUEST_TYPE"
 - "SPB_REQUEST_TYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- spbcx.h
api_name:
- SPB_REQUEST_TYPE
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
---

# _SPB_REQUEST_TYPE enumeration


## -description


The <b>SPB_REQUEST_TYPE</b> enumeration specifies the type of SPB operation that a client is requesting.


## -enum-fields




### -field SpbRequestTypeUndefined

For internal use only.


### -field SpbRequestTypeRead

 A read operation. The transfer direction for read data is from the target device to the client (peripheral driver).  Your SPB controller driver will  see requests of this type only  if it registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a> callback function.


### -field SpbRequestTypeWrite

A write operation. The transfer direction for write data is from the client to the target device.  Your SPB controller driver receives requests of this type only if it registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a> callback function.


### -field SpbRequestTypeSequence

A sequence of transfer (read and write) operations combined into a single request. Your SPB controller driver receives requests of this type only if it registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a> callback function.  Otherwise, the SPB framework extension (SpbCx) will convert an I/O transfer sequence into a series of I/O requests of type <b>SpbRequestTypeRead</b> and <b>SpbRequestTypeWrite</b>, and send these requests to the SPB controller driver's <i>EvtSpbControllerIoRead</i> and <i>EvtSpbControllerIoWrite</i> callback functions.


### -field SpbRequestTypeLockController

A request to lock the controller exclusively for bus transfers to or from the specified target device.  Your SPB controller driver receives requests of this type only if it registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock">EvtSpbControllerLock</a> callback function.


### -field SpbRequestTypeUnlockController

A request to unlock the controller for the specified target device.  Your SPB controller driver receives requests of this type through its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a> callback function.


### -field SpbRequestTypeLockConnection

A request to lock the specified target device for exclusive use by a client.  This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj819324">IOCTL_SPB_LOCK_CONNECTION</a>.


### -field SpbRequestTypeUnlockConnection

A request to unlock the specified target device.  This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj819325">IOCTL_SPB_UNLOCK_CONNECTION</a>.


### -field SpbRequestTypeOther

An unknown I/O control (IOCTL) request sent by a client (peripheral driver) to a target device on the bus.  Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a> method to retrieve the parameters for this request; for this call, use the SPBREQUEST handle for the <i>Request</i> parameter. Your SPB controller driver receives requests of this type only if it registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a> callback function.  Otherwise, SpbCx rejects unknown IOCTL requests.


### -field SpbRequestTypeMax

For internal use only.


## -remarks



The <a href="https://docs.microsoft.com/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a> structure contains an <b>SPB_REQUEST_TYPE</b> enumeration value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_write">EvtSpbControllerIoWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_lock">EvtSpbControllerLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj819324">IOCTL_SPB_LOCK_CONNECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj819325">IOCTL_SPB_UNLOCK_CONNECTION</a>



<a href="https://docs.microsoft.com/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

