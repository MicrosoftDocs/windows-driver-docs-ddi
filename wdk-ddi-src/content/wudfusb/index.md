---
UID: NA:wudfusb
ms.assetid: 1287e4d2-981d-3a09-9dad-4006e24cb476
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wudfusb.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wudfusb.h contain these programming interfaces:


## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_USB_REQUEST_TYPE enumeration](ne-wudfusb-_wdf_usb_request_type.md) | The WDF_USB_REQUEST_TYPE enumeration contains values that identify a type of USB request object. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IUsbTargetPipeContinuousReaderCallbackReadComplete interface](nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete.md) | IUsbTargetPipeContinuousReaderCallbackReadComplete is a driver-supplied interface. |
| [IUsbTargetPipeContinuousReaderCallbackReadersFailed interface](nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed.md) | IUsbTargetPipeContinuousReaderCallbackReadersFailed is a driver-supplied interface. |
| [IWDFUsbInterface interface](nn-wudfusb-iwdfusbinterface.md) | The IWDFUsbInterface interface exposes a USB interface that a USB device exposes. |
| [IWDFUsbRequestCompletionParams interface](nn-wudfusb-iwdfusbrequestcompletionparams.md) | The IWDFUsbRequestCompletionParams interface exposes the parameters object for the completion of a USB request object. The parameters object is primarily required for asynchronous I/O and layered drivers. |
| [IWDFUsbTargetDevice interface](nn-wudfusb-iwdfusbtargetdevice.md) | The IWDFUsbTargetDevice interface exposes a USB device I/O target object. |
| [IWDFUsbTargetFactory interface](nn-wudfusb-iwdfusbtargetfactory.md) | The IWDFUsbTargetFactory interface is a factory interface that is used to create a USB target device object. |
| [IWDFUsbTargetPipe interface](nn-wudfusb-iwdfusbtargetpipe.md) | The IWDFUsbTargetPipe interface exposes a USB pipe (endpoint), which is also an I/O target. |
| [IWDFUsbTargetPipe2 interface](nn-wudfusb-iwdfusbtargetpipe2.md) | The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion method](nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion.md) | A driver's OnReaderCompletion event callback function informs the driver that a continuous reader has successfully completed a read request. |
| [IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method](nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed-onreaderfailure.md) | A driver's OnReaderFailure event callback function informs the driver that a continuous reader has reported an error while processing a read request. |
| [IWDFUsbInterface::GetConfiguredSettingIndex method](nf-wudfusb-iwdfusbinterface-getconfiguredsettingindex.md) | The GetConfiguredSettingIndex method retrieves the current setting index for a USB interface. |
| [IWDFUsbInterface::GetInterfaceDescriptor method](nf-wudfusb-iwdfusbinterface-getinterfacedescriptor.md) | The GetInterfaceDescriptor method retrieves a descriptor for a USB interface. |
| [IWDFUsbInterface::GetInterfaceNumber method](nf-wudfusb-iwdfusbinterface-getinterfacenumber.md) | The GetInterfaceNumber method retrieves the index of a USB interface. |
| [IWDFUsbInterface::GetNumEndPoints method](nf-wudfusb-iwdfusbinterface-getnumendpoints.md) | The GetNumEndPoints method retrieves the number of endpoints (pipes) on a USB interface. |
| [IWDFUsbInterface::GetWinUsbHandle method](nf-wudfusb-iwdfusbinterface-getwinusbhandle.md) | The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a USB interface. |
| [IWDFUsbInterface::RetrieveUsbPipeObject method](nf-wudfusb-iwdfusbinterface-retrieveusbpipeobject.md) | The RetrieveUsbPipeObject method retrieves a USB pipe object for the specified pipe index. |
| [IWDFUsbInterface::SelectSetting method](nf-wudfusb-iwdfusbinterface-selectsetting.md) | The SelectSetting method selects the specified alternate setting on a USB interface. |
| [IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method](nf-wudfusb-iwdfusbrequestcompletionparams-getcompletedusbrequesttype.md) | The GetCompletedUsbRequestType method retrieves the type of operation that the request to be completed contains. |
| [IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters method](nf-wudfusb-iwdfusbrequestcompletionparams-getdevicecontroltransferparameters.md) | The GetDeviceControlTransferParameters method retrieves parameters that are associated with the completion of a device I/O control request. |
| [IWDFUsbRequestCompletionParams::GetPipeReadParameters method](nf-wudfusb-iwdfusbrequestcompletionparams-getpipereadparameters.md) | The GetPipeReadParameters method retrieves parameters that are associated with the completion of a read request. |
| [IWDFUsbRequestCompletionParams::GetPipeWriteParameters method](nf-wudfusb-iwdfusbrequestcompletionparams-getpipewriteparameters.md) | The GetPipeWriteParameters method retrieves parameters that are associated with the completion of a write request. |
| [IWDFUsbTargetDevice::FormatRequestForControlTransfer method](nf-wudfusb-iwdfusbtargetdevice-formatrequestforcontroltransfer.md) | The FormatRequestForControlTransfer method formats an I/O request object for a USB control transfer. |
| [IWDFUsbTargetDevice::GetNumInterfaces method](nf-wudfusb-iwdfusbtargetdevice-getnuminterfaces.md) | The GetNumInterfaces method retrieves the number of USB interfaces for the USB device. |
| [IWDFUsbTargetDevice::GetWinUsbHandle method](nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle.md) | The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a I/O target device object. |
| [IWDFUsbTargetDevice::RetrieveDescriptor method](nf-wudfusb-iwdfusbtargetdevice-retrievedescriptor.md) | The RetrieveDescriptor method retrieves a USB descriptor, which can describe a device, configuration, or string. |
| [IWDFUsbTargetDevice::RetrieveDeviceInformation method](nf-wudfusb-iwdfusbtargetdevice-retrievedeviceinformation.md) | The RetrieveDeviceInformation method retrieves device information of the specified type. |
| [IWDFUsbTargetDevice::RetrievePowerPolicy method](nf-wudfusb-iwdfusbtargetdevice-retrievepowerpolicy.md) | The RetrievePowerPolicy method retrieves a WinUsb power policy. |
| [IWDFUsbTargetDevice::RetrieveUsbInterface method](nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface.md) | The RetrieveUsbInterface method retrieves the specified USB interface for a USB device. |
| [IWDFUsbTargetDevice::SetPowerPolicy method](nf-wudfusb-iwdfusbtargetdevice-setpowerpolicy.md) | The SetPowerPolicy method sets the WinUsb power policy. |
| [IWDFUsbTargetFactory::CreateUsbTargetDevice method](nf-wudfusb-iwdfusbtargetfactory-createusbtargetdevice.md) | The CreateUsbTargetDevice method creates a USB device object that is also an I/O target. |
| [IWDFUsbTargetPipe2::ConfigureContinuousReader method](nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader.md) | The ConfigureContinuousReader method configures the framework to continuously read from a USB pipe. |
| [IWDFUsbTargetPipe::Abort method](nf-wudfusb-iwdfusbtargetpipe-abort.md) | The Abort method aborts all pending transfers on a USB pipe. |
| [IWDFUsbTargetPipe::Flush method](nf-wudfusb-iwdfusbtargetpipe-flush.md) | The Flush method discards any data that WinUsb saved when the device returned more data than the client requested. |
| [IWDFUsbTargetPipe::GetInformation method](nf-wudfusb-iwdfusbtargetpipe-getinformation.md) | The GetInformation method retrieves information about a USB pipe (endpoint). |
| [IWDFUsbTargetPipe::GetType method](nf-wudfusb-iwdfusbtargetpipe-gettype.md) | The GetType method retrieves the type of a USB pipe. |
| [IWDFUsbTargetPipe::IsInEndPoint method](nf-wudfusb-iwdfusbtargetpipe-isinendpoint.md) | The IsInEndPoint method determines whether a USB pipe (endpoint) is an IN pipe. |
| [IWDFUsbTargetPipe::IsOutEndPoint method](nf-wudfusb-iwdfusbtargetpipe-isoutendpoint.md) | The IsOutEndPoint method determines whether a USB pipe (endpoint) is an OUT pipe. |
| [IWDFUsbTargetPipe::Reset method](nf-wudfusb-iwdfusbtargetpipe-reset.md) | The Reset method resets the data toggle and clears the stall condition on a USB pipe. |
| [IWDFUsbTargetPipe::RetrievePipePolicy method](nf-wudfusb-iwdfusbtargetpipe-retrievepipepolicy.md) | The RetrievePipePolicy method retrieves a WinUsb pipe policy. |
| [IWDFUsbTargetPipe::SetPipePolicy method](nf-wudfusb-iwdfusbtargetpipe-setpipepolicy.md) | The SetPipePolicy method sets the WinUsb pipe policy. |
