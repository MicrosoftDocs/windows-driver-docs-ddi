---
UID: NA:wdtfinterfaces
ms.assetid: e172752b-c698-3669-8615-778188cafdb6
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtfinterfaces.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtfinterfaces.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWDTFSimpleIOEx2 interface](nn-wdtfinterfaces-iwdtfsimpleioex2.md) | Defines operations for a simple synchronous I/O functionality test. |
| [IWDTFSimpleIOStressAction2 interface](nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md) | Defines operations for a simple asynchronous I/O functionality test. |
| [IWDTFSimpleIOStressActions2 interface](nn-wdtfinterfaces-iwdtfsimpleiostressactions2.md) | Defines operations for a collection of simple asynchronous I/O functionality tests. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWDTFSimpleIOEx2::Close method](nf-wdtfinterfaces-iwdtfsimpleioex2-close.md) | Closes the device. |
| [IWDTFSimpleIOEx2::Open method](nf-wdtfinterfaces-iwdtfsimpleioex2-open.md) | Opens the device. |
| [IWDTFSimpleIOEx2::PerformIO method](nf-wdtfinterfaces-iwdtfsimpleioex2-performio.md) | Performs a small amount of simple I/O to the device. |
| [IWDTFSimpleIOStressAction2::Continue method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-continue.md) | Continues the I/O. |
| [IWDTFSimpleIOStressAction2::ContinueAsync method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-continueasync.md) | Asynchronously signals the I/O to continue. |
| [IWDTFSimpleIOStressAction2::Pause method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-pause.md) | Pauses the I/O. |
| [IWDTFSimpleIOStressAction2::Start method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-start.md) | Opens the device. |
| [IWDTFSimpleIOStressAction2::StartAsync method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-startasync.md) | Asynchronously signals a start event to occur. |
| [IWDTFSimpleIOStressAction2::Stop method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-stop.md) | Stops the device. |
| [IWDTFSimpleIOStressAction2::StopAsync method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-stopasync.md) | Asynchronously signals the stop event to occur. |
| [IWDTFSimpleIOStressAction2::WaitAsyncCompletion method](nf-wdtfinterfaces-iwdtfsimpleiostressaction2-waitasynccompletion.md) | Waits for the completion of any of the asynchronous events. |
