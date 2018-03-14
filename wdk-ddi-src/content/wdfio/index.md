---
UID: NA:wdfio
ms.assetid: 4c6275da-4fdc-3a43-85f1-9db048bee025
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfio.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfio.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_IO_QUEUE_CONFIG_INIT function](nf-wdfio-wdf_io_queue_config_init.md) | The WDF_IO_QUEUE_CONFIG_INIT function initializes a driver's WDF_IO_QUEUE_CONFIG structure. |
| [WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function](nf-wdfio-wdf_io_queue_config_init_default_queue.md) | The WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function initializes a driver's WDF_IO_QUEUE_CONFIG structure. |
| [WDF_IO_QUEUE_DRAINED function](nf-wdfio-wdf_io_queue_drained.md) | The WDF_IO_QUEUE_DRAINED function returns TRUE if the I/O queue's state indicates that the queue is drained. |
| [WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT function](nf-wdfio-wdf_io_queue_forward_progress_policy_default_init.md) | The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure. |
| [WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function](nf-wdfio-wdf_io_queue_forward_progress_policy_examine_init.md) | The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure. |
| [WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function](nf-wdfio-wdf_io_queue_forward_progress_policy_pagingio_init.md) | The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure. |
| [WDF_IO_QUEUE_IDLE function](nf-wdfio-wdf_io_queue_idle.md) | The WDF_IO_QUEUE_IDLE function returns TRUE if an I/O queue's state indicates that the queue is drained. |
| [WDF_IO_QUEUE_PURGED function](nf-wdfio-wdf_io_queue_purged.md) | The WDF_IO_QUEUE_PURGED function returns TRUE if an I/O queue's state indicates that the queue is drained. |
| [WDF_IO_QUEUE_READY function](nf-wdfio-wdf_io_queue_ready.md) | The WDF_IO_QUEUE_READY function returns TRUE if an I/O queue's state indicates that the queue is drained. |
| [WDF_IO_QUEUE_STOPPED function](nf-wdfio-wdf_io_queue_stopped.md) | The WDF_IO_QUEUE_STOPPED function returns TRUE if an I/O queue's state indicates that the queue is stopped. |
| [WdfIoQueueAssignForwardProgressPolicy function](nf-wdfio-wdfioqueueassignforwardprogresspolicy.md) | The WdfIoQueueAssignForwardProgressPolicy method enables the framework's ability to guarantee forward progress for a specified I/O queue. |
| [WdfIoQueueCreate function](nf-wdfio-wdfioqueuecreate.md) | The WdfIoQueueCreate method creates and configures an I/O queue for a specified device. |
| [WdfIoQueueDrain function](nf-wdfio-wdfioqueuedrain.md) | The WdfIoQueueDrain method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. |
| [WdfIoQueueDrainSynchronously function](nf-wdfio-wdfioqueuedrainsynchronously.md) | The WdfIoQueueDrainSynchronously method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled. |
| [WdfIoQueueFindRequest function](nf-wdfio-wdfioqueuefindrequest.md) | The WdfIoQueueFindRequest method locates the next request in an I/O queue, or the next request that matches specified criteria, but does not grant ownership of the request to the driver. |
| [WdfIoQueueGetDevice function](nf-wdfio-wdfioqueuegetdevice.md) | The WdfIoQueueGetDevice method returns a handle to the framework device object that a specified I/O queue belongs to. |
| [WdfIoQueueGetState function](nf-wdfio-wdfioqueuegetstate.md) | The WdfIoQueueGetState method returns the status of a specified I/O queue. |
| [WdfIoQueuePurge function](nf-wdfio-wdfioqueuepurge.md) | The WdfIoQueuePurge method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests. |
| [WdfIoQueuePurgeSynchronously function](nf-wdfio-wdfioqueuepurgesynchronously.md) | The WdfIoQueuePurgeSynchronously method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests. |
| [WdfIoQueueReadyNotify function](nf-wdfio-wdfioqueuereadynotify.md) | The WdfIoQueueReadyNotify method registers (or deregisters) an event callback function that the framework calls each time a specified I/O queue that was previously empty receives one or more I/O requests. |
| [WdfIoQueueRetrieveFoundRequest function](nf-wdfio-wdfioqueueretrievefoundrequest.md) | The WdfIoQueueRetrieveFoundRequest method delivers a specified request to the driver, so that the driver can process the request. |
| [WdfIoQueueRetrieveNextRequest function](nf-wdfio-wdfioqueueretrievenextrequest.md) | The WdfIoQueueRetrieveNextRequest method retrieves the next available I/O request from a specified I/O queue. |
| [WdfIoQueueRetrieveRequestByFileObject function](nf-wdfio-wdfioqueueretrieverequestbyfileobject.md) | The WdfIoQueueRetrieveRequestByFileObject method retrieves the next available I/O request, from a specified I/O queue, that is associated with a specified file object. |
| [WdfIoQueueStart function](nf-wdfio-wdfioqueuestart.md) | The WdfIoQueueStart method enables an I/O queue to start receiving and delivering new I/O requests. |
| [WdfIoQueueStop function](nf-wdfio-wdfioqueuestop.md) | The WdfIoQueueStop method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. |
| [WdfIoQueueStopAndPurge function](nf-wdfio-wdfioqueuestopandpurge.md) | The WdfIoQueueStopAndPurge method prevents an I/O queue from delivering new requests and cancels existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests. |
| [WdfIoQueueStopAndPurgeSynchronously function](nf-wdfio-wdfioqueuestopandpurgesynchronously.md) | The WdfIoQueueStopAndPurgeSynchronously method prevents an I/O queue from delivering new I/O requests and causes the framework to cancel existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests. |
| [WdfIoQueueStopSynchronously function](nf-wdfio-wdfioqueuestopsynchronously.md) | The WdfIoQueueStopSynchronously method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback](nc-wdfio-evt_wdf_io_allocate_request_resources.md) | A driver's EvtIoAllocateRequestResources callback function allocates request-specific resources that the driver requires to process the specified request. |
| [EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST callback](nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md) | A driver's EvtIoAllocateResourcesForReservedRequest callback function allocates request-specific resources that the driver can use to process an I/O request in the future. |
| [EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE callback](nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md) | A driver's EvtIoCanceledOnQueue event callback function informs the driver that it must complete an I/O request that the framework has removed from an I/O queue. |
| [EVT_WDF_IO_QUEUE_IO_DEFAULT callback](nc-wdfio-evt_wdf_io_queue_io_default.md) | A driver's EvtIoDefault event callback function processes a specified I/O request. |
| [EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback](nc-wdfio-evt_wdf_io_queue_io_device_control.md) | A driver's EvtIoDeviceControl event callback function processes a specified device I/O control request. |
| [EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL callback](nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md) | A driver's EvtIoInternalDeviceControl event callback function processes an I/O request that contains an internal device I/O control code (IOCTL). |
| [EVT_WDF_IO_QUEUE_IO_READ callback](nc-wdfio-evt_wdf_io_queue_io_read.md) | A driver's EvtIoRead event callback function processes a specified read request. |
| [EVT_WDF_IO_QUEUE_IO_RESUME callback](nc-wdfio-evt_wdf_io_queue_io_resume.md) | A driver's EvtIoResume event callback function resumes processing a specified I/O request after the underlying device returns to its working (D0) power state. |
| [EVT_WDF_IO_QUEUE_IO_STOP callback](nc-wdfio-evt_wdf_io_queue_io_stop.md) | A driver's EvtIoStop event callback function completes, requeues, or suspends processing of a specified request because the request's I/O queue is being stopped. |
| [EVT_WDF_IO_QUEUE_IO_WRITE callback](nc-wdfio-evt_wdf_io_queue_io_write.md) | A driver's EvtIoWrite event callback function processes a specified write request. |
| [EVT_WDF_IO_QUEUE_STATE callback](nc-wdfio-evt_wdf_io_queue_state.md) | A driver's EvtIoQueueState event callback function delivers queue state information to the driver. |
| [EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback](nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress.md) | A driver's EvtIoWdmIrpForForwardProgress callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure](ns-wdfio-_wdf_io_forward_progress_reserved_policy_settings.md) | The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists. |
| [_WDF_IO_QUEUE_CONFIG structure](ns-wdfio-_wdf_io_queue_config.md) | The WDF_IO_QUEUE_CONFIG structure contains configuration information for a framework queue object. |
| [_WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure](ns-wdfio-_wdf_io_queue_forward_progress_policy.md) | The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure contains driver-supplied information that the framework uses to enable guaranteed forward progress for an I/O queue. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_IO_FORWARD_PROGRESS_ACTION enumeration](ne-wdfio-_wdf_io_forward_progress_action.md) | The WDF_IO_FORWARD_PROGRESS_ACTION enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation. |
| [_WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration](ne-wdfio-_wdf_io_forward_progress_reserved_policy.md) | The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration identifies actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists. |
| [_WDF_IO_QUEUE_DISPATCH_TYPE enumeration](ne-wdfio-_wdf_io_queue_dispatch_type.md) | The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object. |
| [_WDF_IO_QUEUE_STATE enumeration](ne-wdfio-_wdf_io_queue_state.md) | The WDF_IO_QUEUE_STATE enumeration type identifies the status of a framework queue object. The enumerators are used as bit masks. |
