---
UID: NF:spbcx.SpbControllerSetIoOtherCallback
title: SpbControllerSetIoOtherCallback function (spbcx.h)
description: The SpbControllerSetIoOtherCallback method registers an SPB controller driver's EvtSpbControllerIoOther callback function.
old-location: spb\spbcontrollersetioothercallback.htm
tech.root: SPB
ms.assetid: 605E2353-8C82-4005-BB72-4CB44146A253
ms.date: 04/30/2018
keywords: ["SpbControllerSetIoOtherCallback function"]
ms.keywords: SPB.spbcontrollersetioothercallback, SpbControllerSetIoOtherCallback, SpbControllerSetIoOtherCallback method [Buses], spbcx/SpbControllerSetIoOtherCallback
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SpbControllerSetIoOtherCallback
 - spbcx/SpbControllerSetIoOtherCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - spbcxstubs.lib
 - spbcxstubs.dll
api_name:
 - SpbControllerSetIoOtherCallback
---

# SpbControllerSetIoOtherCallback function


## -description

The <b>SpbControllerSetIoOtherCallback</b> method registers an SPB controller driver's <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a> callback function.

## -parameters

### -param FxDevice 

[in]
A WDFDEVICE handle to the device object that represents the SPB controller.

### -param EvtSpbControllerIoOther 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a> callback function. The SPB controller driver implements this function. The SPB framework extension (SpbCx) calls this function to pass an I/O control request to the controller driver. For more information about the type of I/O requests that are passed to this function, see the following Remarks section.

### -param EvtIoInCallerContext 

[in, optional]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function that is called when an I/O control request first arrives at the controller's I/O queue, and the request contains an IOCTL code that the SPB framework extension (SpbCx) does not recognize. This callback runs in the process context of the request originator, and can preprocess requests that will later be processed by the <i>EvtSpbControllerIoOther</i> callback. This parameter is optional and can be specified as NULL if no such preprocessing is required. For more information, see the following Remarks section.

## -remarks

This method provides a way for your SPB controller driver to declare its support for custom I/O control codes (IOCTLs) that are bus-specific or driver-specific. If the SPB controller driver does not call this method, SpbCx rejects all such I/O control requests, and the SPB controller driver never sees them.

SpbCx manages the I/O queue for the SPB controller. By default, if SpbCx receives an I/O control request that has an IOCTL that it does not support, SpbCx completes the request with error status code STATUS_INVALID_DEVICE_REQUEST.

However, by calling <b>SpbControllerSetIoOtherCallback</b>, the SPB controller driver declares its support for I/O control requests that the SPB framework extension (SpbCx) does not support. In this case, when SpbCx receives an I/O control request that has an IOCTL code that it does not support, SpbCx calls the <i>EvtSpbControllerIoOther</i> function to pass the request to the SPB controller driver for processing. The SPB controller driver is responsible for completing the request.

For a list of the IOCTLs that SpbCx supports, see <a href="/previous-versions/hh450915(v=vs.85)">SpbCx I/O Control Codes</a>.

The optional <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function runs in the process context of the request originator, and can preprocess context-dependent request parameters, such as buffer pointers, before the request is passed to the <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a> callback function.  When the <i>EvtIoInCallerContext</i> function is called, any per-request context that the SPB controller driver requested in a previous call to <a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbcontrollersetrequestattributes">SpbControllerSetRequestAttributes</a> will already be allocated and assigned to the request.

The SPB controller driver must call this method before it <i>commits</i> the device object—that is, before it returns from the <i>EvtDriverDeviceAdd</i> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbcontrollersetrequestattributes">SpbControllerSetRequestAttributes</a>