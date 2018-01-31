---
UID: NC:spbcx.EVT_SPB_CONTROLLER_READ
title: EVT_SPB_CONTROLLER_READ
author: windows-driver-content
description: An SPB controller driver's EvtSpbControllerIoRead event callback function reads data from the specified target device into the buffers that are supplied with the read request.
old-location: spb\evtspbcontrollerioread.htm
old-project: SPB
ms.assetid: 2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB.evtspbcontrollerioread, EvtSpbControllerIoRead callback function [Buses], EvtSpbControllerIoRead, EVT_SPB_CONTROLLER_READ, EVT_SPB_CONTROLLER_READ, spbcx/EvtSpbControllerIoRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Spbcx.h
apiname:
-	EvtSpbControllerIoRead
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_LIST_ENTRY, *PSPB_TRANSFER_LIST_ENTRY
req.product: Windows 10 or later.
---

# EVT_SPB_CONTROLLER_READ callback


## -description


An SPB controller driver's <i>EvtSpbControllerIoRead</i> event callback function reads data from the specified target device into the buffers that are supplied with the read request.


## -prototype


````
EVT_SPB_CONTROLLER_READ EvtSpbControllerIoRead;

VOID EvtSpbControllerIoRead(
  _In_ WDFDEVICE  Controller,
  _In_ SPBTARGET  Target,
  _In_ SPBREQUEST Request,
  _In_ size_t     Length
)
{ ... }
````


## -parameters




#### - Controller [in]

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.


#### - Target [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.


#### - Request [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.


#### - Length [in]

The number of bytes to read from the target device.


## -returns


None.



## -remarks


SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's <i>EvtSpbControllerIoRead</i> callback function when a client (peripheral driver) of the SPB controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request to a target device that is attached to the bus. The <i>Request</i> parameter value is a handle that encapsulates this request.

An <i>EvtSpbControllerIoRead</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the read operation in the completion status for the I/O request.

An <i>EvtSpbControllerIoRead</i> callback is asynchronous.  That is, the callback function should initiate the requested read operation and then return without waiting for the operation to complete. Later, the SPB controller driver completes the read request during an interrupt DPC or a timer DPC.

If the read operation completes in full, the SPB controller driver should set the completion status to  STATUS_SUCCESS. If the target device indicates that it can supply some but not all  of the data requested, the SPB controller driver should retrieve as much data as is available, specify the number of data bytes retrieved, and set the completion status in the I/O request to  STATUS_SUCCESS. Such a partially completed read operation cannot occur on an SPI or I²C bus, but might occur on another type of bus.

If the read operation fails due to line noise, a controller hardware error, or a driver error, then the SPB controller driver should set the completion status in the I/O request to an appropriate error code. Not all buses provide a mechanism for a target device to report a transport error or a partially completed transfer, and not all controllers can detect these conditions.

To register an <i>EvtSpbControllerIoRead</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.



## -see-also

<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>

<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20EVT_SPB_CONTROLLER_READ callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

