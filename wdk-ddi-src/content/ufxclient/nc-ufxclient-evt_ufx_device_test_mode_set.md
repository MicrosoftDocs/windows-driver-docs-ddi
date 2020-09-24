---
UID: NC:ufxclient.EVT_UFX_DEVICE_TEST_MODE_SET
title: EVT_UFX_DEVICE_TEST_MODE_SET (ufxclient.h)
description: The client driver's implementation to set the test mode of the function controller.
old-location: buses\evt_ufx_device_test_mode_set.htm
tech.root: usbref
ms.assetid: 24B17B8E-C2F0-4CA8-AA9D-5EE86EB20CCC
ms.date: 05/07/2018
keywords: ["EVT_UFX_DEVICE_TEST_MODE_SET callback function"]
ms.keywords: EVT_UFX_DEVICE_TEST_MODE_SET, EVT_UFX_DEVICE_TEST_MODE_SET callback, EvtUfxDeviceTestModeSet, EvtUfxDeviceTestModeSet callback function [Buses], PFN_UFX_DEVICE_TEST_MODE_SET, PFN_UFX_DEVICE_TEST_MODE_SET callback function pointer [Buses], buses.evt_ufx_device_test_mode_set, ufxclient/EvtUfxDeviceTestModeSet
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_TEST_MODE_SET
 - ufxclient/EVT_UFX_DEVICE_TEST_MODE_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - PFN_UFX_DEVICE_TEST_MODE_SET
---

# EVT_UFX_DEVICE_TEST_MODE_SET callback function


## -description

The client driver's implementation to set the test mode of the function controller.

## -parameters

#### - TestMode [in]

Test mode selector value as defined by the USB 2.0 Specification.  These values are defined in usbfnbase.h

<ul>
<li>USB_TEST_MODE_TEST_J              0x01</li>
<li>USB_TEST_MODE_TEST_K              0x02
</li>
<li>USB_TEST_MODE_TEST_SE0_NAK        0x03
</li>
<li>USB_TEST_MODE_TEST_PACKET         0x04
</li>
<li>USB_TEST_MODE_TEST_FORCE_ENABLE   0x05
</li>
</ul>

#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

## -remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_TEST_MODE_SET</i> implementation with the USB function class extension (UFX) by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples


```
EVT_UFX_DEVICE_TEST_MODE_SET UfxDevice_EvtDeviceTestModeSet;

VOID
UfxDevice_EvtDeviceTestModeSet (
    _In_ UFXDEVICE UfxDevice,
    _In_ ULONG TestMode
    )
/*++

Routine Description:

    EvtDeviceTestModeSet handler for the UFXDEVICE object.
    
    Handles a set test mode request from the host.  Places the controller into 
    the specified test mode.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    TestMode - Test mode value.  See Section 7.1.20 of the USB 2.0 specification for definitions of 
               each test mode.

--*/
{
    NTSTATUS Status;

    UNREFERENCED_PARAMETER(TestMode);

    TraceEntry();

    //
    // #### TODO: Insert code to put the controller into the specified test mode ####
    //

    Status = STATUS_SUCCESS;

    UfxDeviceEventComplete(UfxDevice, Status);
    TraceExit();
}

```


## -see-also

<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>