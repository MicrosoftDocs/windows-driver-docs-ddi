---
UID: NF:spbcx.SpbControllerSetIoOtherCallback
title: SpbControllerSetIoOtherCallback function
author: windows-driver-content
description: The SpbControllerSetIoOtherCallback method registers an SPB controller driver's EvtSpbControllerIoOther callback function.
old-location: spb\spbcontrollersetioothercallback.htm
old-project: SPB
ms.assetid: 605E2353-8C82-4005-BB72-4CB44146A253
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: spbcx/SpbControllerSetIoOtherCallback, SpbControllerSetIoOtherCallback, SPB.spbcontrollersetioothercallback, SpbControllerSetIoOtherCallback method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	spbcxstubs.lib
-	spbcxstubs.dll
apiname:
-	SpbControllerSetIoOtherCallback
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbControllerSetIoOtherCallback function


## -description


The <b>SpbControllerSetIoOtherCallback</b> method registers an SPB controller driver's <a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a> callback function.


## -syntax


````
VOID SpbControllerSetIoOtherCallback(
  _In_     WDFDEVICE                    FxDevice,
  _In_     PFN_SPB_CONTROLLER_IO_OTHER  EvtSpbControllerIoOther,
  _In_opt_ PFN_WDF_IO_IN_CALLER_CONTEXT EvtIoInCallerContext
);
````


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the device object that represents the SPB controller.


### -param EvtSpbControllerIoOther [in]

A pointer to an <a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a> callback function. The SPB controller driver implements this function. The SPB framework extension (SpbCx) calls this function to pass an I/O control request to the controller driver. For more information about the type of I/O requests that are passed to this function, see the following Remarks section.


### -param EvtIoInCallerContext [in, optional]

A pointer to an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function that is called when an I/O control request first arrives at the controller's I/O queue, and the request contains an IOCTL code that the SPB framework extension (SpbCx) does not recognize. This callback runs in the process context of the request originator, and can preprocess requests that will later be processed by the <i>EvtSpbControllerIoOther</i> callback. This parameter is optional and can be specified as NULL if no such preprocessing is required. For more information, see the following Remarks section.


## -returns



None.




## -remarks



This method provides a way for your SPB controller driver to declare its support for custom I/O control codes (IOCTLs) that are bus-specific or driver-specific. If the SPB controller driver does not call this method, SpbCx rejects all such I/O control requests, and the SPB controller driver never sees them.

SpbCx manages the I/O queue for the SPB controller. By default, if SpbCx receives an I/O control request that has an IOCTL that it does not support, SpbCx completes the request with error status code STATUS_INVALID_DEVICE_REQUEST.

However, by calling <b>SpbControllerSetIoOtherCallback</b>, the SPB controller driver declares its support for I/O control requests that the SPB framework extension (SpbCx) does not support. In this case, when SpbCx receives an I/O control request that has an IOCTL code that it does not support, SpbCx calls the <i>EvtSpbControllerIoOther</i> function to pass the request to the SPB controller driver for processing. The SPB controller driver is responsible for completing the request.

For a list of the IOCTLs that SpbCx supports, see <a href="https://msdn.microsoft.com/EED1CBA4-8691-4BEA-89CB-F93DD7E1874F">SpbCx I/O Control Codes</a>.

The optional <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function runs in the process context of the request originator, and can preprocess context-dependent request parameters, such as buffer pointers, before the request is passed to the <a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a> callback function.  When the <i>EvtIoInCallerContext</i> function is called, any per-request context that the SPB controller driver requested in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh450908">SpbControllerSetRequestAttributes</a> will already be allocated and assigned to the request.

The SPB controller driver must call this method before it <i>commits</i> the device object—that is, before it returns from the <i>EvtDriverDeviceAdd</i> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="https://msdn.microsoft.com/5731db82-2bc8-4a8d-98f1-3977845f572c">Enumerating the Devices on a Bus</a>.




## -see-also

<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450908">SpbControllerSetRequestAttributes</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbControllerSetIoOtherCallback method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

