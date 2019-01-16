---
UID: NF:ufxclient.UfxDeviceCreate
title: UfxDeviceCreate function
description: Creates a UFX device object, registers event callback routines, and specifies capabilities specific to the controller.
old-location: buses\ufxdevicecreate.htm
tech.root: usbref
ms.assetid: BA86280E-8324-4D98-B16C-504D427A6A4B
ms.date: 05/07/2018
ms.keywords: UfxDeviceCreate, UfxDeviceCreate method [Buses], buses.ufxdevicecreate, ufxclient/UfxDeviceCreate
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceCreate function


## -description


Creates a UFX device object, registers event callback routines, and specifies capabilities specific to the controller.


## -parameters




### -param WdfDevice

<p>A handle to a WDF device object.</p>


### -param Callbacks [in]

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> that contains pointers to driver-supplied callback routines to be associated with the UFX device object.


### -param Capabilities [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187973">UFX_DEVICE_CAPABILITIES</a> structure.


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param UfxDevice [out]

A pointer to a location that receives a handle to the new UFX device object.




## -returns



If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> before it calls <b>UfxDeviceCreate</b>. Typically, the client driver calls  <b>UfxDeviceCreate</b> from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback routine.

The following code snippet shows how to call <b>UfxDeviceCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UfxDevice_DeviceCreate (
    _In_ WDFDEVICE WdfDevice
    )
/*++

Routine Description:

    Routine that registers with UFX and creates the UFX device object.

Arguments:

    WdfDevice - Wdf object representing the device.

Return Value:

    NTSTATUS.

--*/
{
    NTSTATUS Status;
    PCONTROLLER_CONTEXT ControllerContext;
    UFX_DEVICE_CALLBACKS UfxDeviceCallbacks;
    UFX_DEVICE_CAPABILITIES UfxDeviceCapabilities;
    PUFXDEVICE_CONTEXT UfxDeviceContext;
    UFXDEVICE UfxDevice;
    WDF_OBJECT_ATTRIBUTES Attributes;

    PAGED_CODE();

    TraceEntry();

    ControllerContext = DeviceGetControllerContext(WdfDevice);

    UFX_DEVICE_CAPABILITIES_INIT(&amp;UfxDeviceCapabilities);
    UfxDeviceCapabilities.MaxSpeed = UsbSuperSpeed;
    UfxDeviceCapabilities.RemoteWakeSignalDelay = REMOTE_WAKEUP_TIMEOUT_INTERVAL_MS;
    
    //
    // Set bitmasks that define the IN and OUT endpoint numbers that are available on the controller
    //
    
    //
    // #### TODO: Set the IN endpoint mask here if not all endpoint addresses are supported ####
    //
    // For illustration purposes sample will set default control endpoint 0, 1-4, 8
    UfxDeviceCapabilities.InEndpointBitmap = 0x011F;
    
    //
    // #### TODO: Set the OUT endpoint mask here if not all endpoint addresses are supported ####
    //
    // For illustration purposes sample will set default control endpoint 0, 2-7
    //
    UfxDeviceCapabilities.OutEndpointBitmap = 0x00FD;

    //
    // Set the event callbacks for the ufxdevice
    //
    UFX_DEVICE_CALLBACKS_INIT(&amp;UfxDeviceCallbacks);
    UfxDeviceCallbacks.EvtDeviceHostConnect = UfxDevice_EvtDeviceHostConnect;
    UfxDeviceCallbacks.EvtDeviceHostDisconnect = UfxDevice_EvtDeviceHostDisconnect;
    UfxDeviceCallbacks.EvtDeviceAddressed = UfxDevice_EvtDeviceAddressed;
    UfxDeviceCallbacks.EvtDeviceEndpointAdd = UfxDevice_EvtDeviceEndpointAdd;
    UfxDeviceCallbacks.EvtDeviceDefaultEndpointAdd = UfxDevice_EvtDeviceDefaultEndpointAdd;
    UfxDeviceCallbacks.EvtDeviceUsbStateChange = UfxDevice_EvtDeviceUsbStateChange;
    UfxDeviceCallbacks.EvtDevicePortChange = UfxDevice_EvtDevicePortChange;
    UfxDeviceCallbacks.EvtDevicePortDetect = UfxDevice_EvtDevicePortDetect;
    UfxDeviceCallbacks.EvtDeviceRemoteWakeupSignal = UfxDevice_EvtDeviceRemoteWakeupSignal;
    UfxDeviceCallbacks.EvtDeviceTestModeSet = UfxDevice_EvtDeviceTestModeSet;
    UfxDeviceCallbacks.EvtDeviceSuperSpeedPowerFeature = UfxDevice_EvtDeviceSuperSpeedPowerFeature;

    // Context associated with UFXDEVICE object
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;Attributes, UFXDEVICE_CONTEXT);
    Attributes.EvtCleanupCallback = UfxDevice_EvtCleanupCallback;

    // Create the UFXDEVICE object
    Status = UfxDeviceCreate(WdfDevice,
                             &amp;UfxDeviceCallbacks,
                             &amp;UfxDeviceCapabilities,
                             &amp;Attributes,
                             &amp;UfxDevice);

    ...

}</pre>
</td>
</tr>
</table></span></div>


