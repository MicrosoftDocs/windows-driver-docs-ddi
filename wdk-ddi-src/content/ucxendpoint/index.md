---
UID: NA:ucxendpoint
ms.assetid: f85771e9-a9a2-3525-a86f-44c04d24a9a4
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucxendpoint.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucxendpoint.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT function](nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init.md) | Initializes a UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure with client driver's callback functions. The client driver calls this function before calling UcxEndpointCreate method to create an endpoint and register its callback functions with UCX. |
| [UCX_ENDPOINT_EVENT_CALLBACKS_INIT function](nf-ucxendpoint-ucx_endpoint_event_callbacks_init.md) | Initializes a UCX_ENDPOINT_EVENT_CALLBACKS structure with client driver's callback functions. The client driver calls this function before calling UcxEndpointCreate method to create an endpoint and register its callback functions with UCX. |
| [UcxDefaultEndpointInitSetEventCallbacks function](nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md) | Initializes a UCXENDPOINT_INIT structure with client driver's event callback functions related to the default endpoint. |
| [UcxEndpointAbortComplete function](nf-ucxendpoint-ucxendpointabortcomplete.md) | Notifies UCX that a transfer abort operation has been completed on the specified endpoint object. |
| [UcxEndpointCreate function](nf-ucxendpoint-ucxendpointcreate.md) | Creates an endpoint on the specified USB device object. |
| [UcxEndpointGetStaticStreamsReferenced function](nf-ucxendpoint-ucxendpointgetstaticstreamsreferenced.md) | Returns a referenced static streams object for the specified endpoint. |
| [UcxEndpointInitSetEventCallbacks function](nf-ucxendpoint-ucxendpointinitseteventcallbacks.md) | Initializes a UCXENDPOINT_INIT structure with client driver's event callback functions related to endpoints on the device. |
| [UcxEndpointNeedToCancelTransfers function](nf-ucxendpoint-ucxendpointneedtocanceltransfers.md) | The client driver calls this method before it cancels transfers on the wire. |
| [UcxEndpointNoPingResponseError function](nf-ucxendpoint-ucxendpointnopingresponseerror.md) | Notifies UCX about a &#0034;No Ping Response&#0034; error for a transfer on the specified endpoint object. |
| [UcxEndpointPurgeComplete function](nf-ucxendpoint-ucxendpointpurgecomplete.md) | Notifies UCX that a purge operation has been completed on the specified endpoint object. |
| [UcxEndpointSetWdfIoQueue function](nf-ucxendpoint-ucxendpointsetwdfioqueue.md) | Sets a framework queue on the specified endpoint object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback](nc-ucxendpoint-evt_ucx_default_endpoint_update.md) | The client driver's implementation that UCX calls with information about the default endpoint. |
| [EVT_UCX_ENDPOINT_ABORT callback](nc-ucxendpoint-evt_ucx_endpoint_abort.md) | The client driver's implementation that UCX calls to abort the queue associated with the endpoint. |
| [EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS callback](nc-ucxendpoint-evt_ucx_endpoint_get_isoch_transfer_path_delays.md) | UCX invokes this callback function to get information about transfer path delays for an isochronous endpoint. |
| [EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback](nc-ucxendpoint-evt_ucx_endpoint_ok_to_cancel_transfers.md) | The client driver's implementation that UCX calls to notify the controller driver that it can complete cancelled transfers on the endpoint. |
| [EVT_UCX_ENDPOINT_PURGE callback](nc-ucxendpoint-evt_ucx_endpoint_purge.md) | The client driver's implementation that completes all outstanding I/O requests on the endpoint. |
| [EVT_UCX_ENDPOINT_RESET callback](nc-ucxendpoint-evt_ucx_endpoint_reset.md) | The client driver's implementation that UCX calls to reset the controller’s programming for an endpoint. |
| [EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback](nc-ucxendpoint-evt_ucx_endpoint_set_characteristic.md) | UCX invokes this callback function to set the priority on an endpoint. |
| [EVT_UCX_ENDPOINT_START callback](nc-ucxendpoint-evt_ucx_endpoint_start.md) | The client driver's implementation that UCX calls to start the queue associated with the endpoint. |
| [EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback](nc-ucxendpoint-evt_ucx_endpoint_static_streams_add.md) | The client driver's implementation that UCX calls to create static streams. |
| [EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE callback](nc-ucxendpoint-evt_ucx_endpoint_static_streams_disable.md) | The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint. |
| [EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE callback](nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable.md) | The client driver's implementation that UCX calls to enable the static streams. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_DEFAULT_ENDPOINT_UPDATE structure](ns-ucxendpoint-_default_endpoint_update.md) | Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function. |
| [_ENDPOINTS_CONFIGURE structure](ns-ucxendpoint-_endpoints_configure.md) | Describes endpoints to enable or disable endpoints. This structure is passed by UCX in the EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function. |
| [_ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure](ns-ucxendpoint-_endpoints_configure_failure_flags.md) | This structure provides failure flags to indicate errors, if any, that might have occurred during a request to an EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function. |
| [_ENDPOINT_RESET structure](ns-ucxendpoint-_endpoint_reset.md) | Describes information required to reset an endpoint. This structure is passed by UCX in the EVT_UCX_ENDPOINT_RESET callback function. |
| [_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure](ns-ucxendpoint-_ucx_default_endpoint_event_callbacks.md) | This structure provides a list of UCX default endpoint event callback functions. |
| [_UCX_ENDPOINT_CHARACTERISTIC structure](ns-ucxendpoint-_ucx_endpoint_characteristic.md) | Stores the characteristics of an endpoint. |
| [_UCX_ENDPOINT_EVENT_CALLBACKS structure](ns-ucxendpoint-_ucx_endpoint_event_callbacks.md) | This structure provides a list of pointers to UCX endpoint event callback functions. |
| [_UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS structure](ns-ucxendpoint-_ucx_endpoint_isoch_transfer_path_delays.md) | Stores the isochronous transfer path delay values. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_ENDPOINT_RESET_FLAGS enumeration](ne-ucxendpoint-_endpoint_reset_flags.md) | Defines parameters for a request to reset an endpoint. |
| [_UCX_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration](ne-ucxendpoint-_ucx_endpoint_characteristic_priority.md) | Indicates the priority of endpoints. |
| [_UCX_ENDPOINT_CHARACTERISTIC_TYPE enumeration](ne-ucxendpoint-_ucx_endpoint_characteristic_type.md) | Defines values that indicates the type of endpoint characteristic. |
