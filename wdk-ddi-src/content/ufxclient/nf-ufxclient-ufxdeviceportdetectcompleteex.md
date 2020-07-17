---
UID: NF:ufxclient.UfxDevicePortDetectCompleteEx
title: UfxDevicePortDetectCompleteEx function (ufxclient.h)
description: Notifies UFX about the port type that was detected, and optionally requests an action.
old-location: buses\ufxdeviceportdetectcompleteex.htm
tech.root: usbref
ms.assetid: EB3A65B5-EB21-45CA-B26D-F57A28F9F2CB
ms.date: 05/07/2018
keywords: ["UfxDevicePortDetectCompleteEx function"]
ms.keywords: UfxDevicePortDetectCompleteEx, UfxDevicePortDetectCompleteEx method [Buses], buses.ufxdeviceportdetectcompleteex, ufxclient/UfxDevicePortDetectCompleteEx
f1_keywords:
 - "ufxclient/UfxDevicePortDetectCompleteEx"
 - "UfxDevicePortDetectCompleteEx"
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ufxclient.h
api_name:
- UfxDevicePortDetectCompleteEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDevicePortDetectCompleteEx function


## -description


Notifies UFX about the port type that was detected, and optionally requests an action.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


### -param PortType [in]

Contains an enumeration value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_port_type">USBFN_PORT_TYPE</a>.


### -param Action [in]

Contains an enumeration value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxbase/ne-ufxbase-_usbfn_action">USBFN_ACTION</a>.


## -remarks



The client driver calls <b>UfxDevicePortDetectCompleteEx</b> after port detection is complete, typically from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_port_detect">EVT_UFX_DEVICE_PORT_DETECT</a> callback function. On some platforms, UFX may use the reported port type to notify the battery manager of the maximum current it can draw from the USB port.

  
If the <i>Action</i> parameter is set to <b>UsbfnActionNoCad</b>, UFX does not notify the battery manager at all.


If the <i>Action</i> parameter is set to <b>UsbfnActionDetectProprietaryCharger</b>, UFX requests that the client driver initiate proprietary charger detection by calling the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_detect">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.


The following snippet shows how a client driver calls <b>UfxDevicePortDetectCompleteEx</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    switch (OnAttach.AttachAction) {
    case UsbfnPortDetected:
        TraceInformation("Port Detected");
        UfxDevicePortDetectComplete(
            ControllerData->UfxDevice,
            OnAttach.PortType);

        break;

    case UsbfnPortDetectedNoCad:
        TraceInformation("Port Detected No CAD");
        UfxDevicePortDetectCompleteEx(
            ControllerData->UfxDevice,
            OnAttach.PortType,
            UsbfnActionNoCad);

        break;

</pre>
</td>
</tr>
</table></span></div>


