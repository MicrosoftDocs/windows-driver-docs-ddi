---
UID: NC:d3dkmddi.DXGKDDI_PRESENTDISPLAYONLY
title: DXGKDDI_PRESENTDISPLAYONLY (d3dkmddi.h)
description: Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).
old-location: display\dxgkddipresentdisplayonly.htm
ms.assetid: b68839e3-ad82-4fcc-8e5a-02dea5db08d9
ms.date: 05/10/2018
ms.keywords: DXGKDDI_PRESENTDISPLAYONLY, DXGKDDI_PRESENTDISPLAYONLY callback, DxgkDdiPresentDisplayOnly, DxgkDdiPresentDisplayOnly callback function [Display Devices], d3dkmddi/DxgkDdiPresentDisplayOnly, display.dxgkddipresentdisplayonly
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkDdiPresentDisplayOnly"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmddi.h
api_name:
- DxgkDdiPresentDisplayOnly
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_PRESENTDISPLAYONLY callback function


## -description


Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).


## -parameters




### -param hAdapter [in]

A handle to the device context for the display adapter. The KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously returned this handle in the <i>MiniportDeviceContext</i> parameter.


### -param pPresentDisplayOnly [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present_displayonly">DXGKARG_PRESENT_DISPLAYONLY</a> structure that contains information about the present operation.


## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** |The present operation completed successfully. | 
| **STATUS_PENDING** | The present operation has been sent to the software or hardware queue to complete. <br/>In this case, the KMDOD should use an interrupt and deferred procedure call (DPC) to report progress of the current present operation. Otherwise the operating system uses the [Timeout Detection and Recovery (TDR)](https://docs.microsoft.com/windows-hardware/drivers/display/timeout-detection-and-recovery)  process, which reports an error and requires the KMDOD to reinitialize itself and to reset the GPU.<br/>Note that this status code should not be returned for synchronous mode, as described in Remarks. | 

 

The driver can also return any other error status code defined in Ntstatus.h to indicate issues that have occurred with the present operation.




## -remarks



The KMDOD must complete all screen-to-screen moves before copying dirty rectangles. In addition, the KMDOD must complete each move/copy operation before beginning another move/copy operation.

The operating system supports two modes of KMDOD present operations: synchronous and asynchronous. Depending on hardware and driver implementation, the KMDOD can use either mode or switch between them at any time.



The operating system guarantees that this function follows the  zero level  synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level">Threading and Synchronization Zero Level</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present_displayonly">DXGKARG_PRESENT_DISPLAYONLY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxgkcbpresentdisplayonlyprogress">DxgkCbPresentDisplayOnlyProgress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkcb_queue_dpc">DxgkCbQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

