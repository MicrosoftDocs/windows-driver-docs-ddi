---
UID: NC:ufxclient.EVT_UFX_DEVICE_ADDRESSED
title: EVT_UFX_DEVICE_ADDRESSED (ufxclient.h)
description: The client driver's implementation to assign an address on the function controller.
old-location: buses\evt_ufx_device_addressed.htm
tech.root: usbref
ms.assetid: 99120A01-4674-465A-BA75-58F1871BB820
ms.date: 05/07/2018
keywords: ["EVT_UFX_DEVICE_ADDRESSED callback function"]
ms.keywords: EVT_UFX_DEVICE_ADDRESSED, EVT_UFX_DEVICE_ADDRESSED callback, EvtUfxDeviceAddressed, EvtUfxDeviceAddressed callback function [Buses], PFN_UFX_DEVICE_ADDRESSED, PFN_UFX_DEVICE_ADDRESSED callback function pointer [Buses], buses.evt_ufx_device_addressed, ufxclient/EvtUfxDeviceAddressed
f1_keywords:
 - "ufxclient/PFN_UFX_DEVICE_ADDRESSED"
 - "PFN_UFX_DEVICE_ADDRESSED"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ufxclient.h
api_name:
- PFN_UFX_DEVICE_ADDRESSED
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_ADDRESSED callback function


## -description


The client driver's implementation to assign an address on the function controller.


## -parameters












#### - DeviceAddress [in]

New USB device address to assign. 


#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_ADDRESSED</i> implementation with the USB function class extension (UFX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_ADDRESSED UfxDevice_EvtDeviceAddressed;

VOID
UfxDevice_EvtDeviceAddressed (
    _In_ UFXDEVICE UfxDevice,
    _In_ USHORT DeviceAddress
    )
/*++

Routine Description:

    EvtDeviceAddressed handler for the UFXDEVICE object.
    Sets the Address indicated by 'DeviceAddress' on the controller.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    DeviceAddress - USB Device Address, as determined by the UFX.

--*/
{
    UNREFERENCED_PARAMETER(DeviceAddress);

    TraceEntry();

    //
    // Set the device address on the controller
    //

    //
    // #### Insert code to set the device address on controller ####
    //
    
    UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);

    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
 

 

