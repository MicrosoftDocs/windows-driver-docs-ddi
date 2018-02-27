---
UID: NA:ksproxy
ms.assetid: d1260539-6401-3b8d-b402-dbda616a5e84
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ksproxy.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Ksproxy.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [KsGetMediaType function](nf-ksproxy-ksgetmediatype.md) | The KsGetMediaType function retrieves information about a media type on a pin factory identifier. |
| [KsGetMediaTypeCount function](nf-ksproxy-ksgetmediatypecount.md) | The KsGetMediaTypeCount function returns the number of available media types on a pin factory identifier. |
| [KsGetMultiplePinFactoryItems function](nf-ksproxy-ksgetmultiplepinfactoryitems.md) | The KsGetMultiplePinFactoryItems function retrieves pin property items in a variable length data buffer. |
| [KsOpenDefaultDevice function](nf-ksproxy-ksopendefaultdevice.md) | The KsOpenDefaultDevice function opens a handle to the first device that is listed in the specified Plug and Play (PnP) category. |
| [KsResolveRequiredAttributes function](nf-ksproxy-ksresolverequiredattributes.md) | The KsResolveRequiredAttributes function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found. |
| [KsSynchronousDeviceControl function](nf-ksproxy-kssynchronousdevicecontrol.md) | The KsSynchronousDeviceControl function issues a synchronous device I/O control operation to the KS object that is specified by a file handle. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [OPTIMAL_WEIGHT_TOTALS structure](ns-ksproxy-optimal_weight_totals.md) | "." |
| [_ALLOCATOR_PROPERTIES_EX structure](ns-ksproxy-_allocator_properties_ex.md) | The ALLOCATOR_PROPERTIES_EX structure is for proxy use and not recommended for application use. ALLOCATOR_PROPERTIES_EX contains information that describes properties of an allocator. |
| [_KSSTREAM_SEGMENT structure](ns-ksproxy-_ksstream_segment.md) | The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream. |
| [_PIPE_DIMENSIONS structure](ns-ksproxy-_pipe_dimensions.md) | The PIPE_DIMENSIONS structure is for proxy use and not recommended for application use. PIPE_DIMENSIONS contains information that describes the compression/expansion ratio of frames on various pins related to a pipe. |
| [_PIPE_TERMINATION structure](ns-ksproxy-_pipe_termination.md) | The PIPE_TERMINATION structure is for proxy use and not recommended for application use. PIPE_TERMINATION contains information that describes the pin terminator of a pipe. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [FRAMING_CACHE_OPS enumeration](ne-ksproxy-framing_cache_ops.md) | "." |
| [FRAMING_PROP enumeration](ne-ksproxy-framing_prop.md) | "." |
| [KSALLOCATORMODE enumeration](ne-ksproxy-ksallocatormode.md) | "." |
| [KSIOOPERATION enumeration](ne-ksproxy-ksiooperation.md) | "." |
| [KSPEEKOPERATION enumeration](ne-ksproxy-kspeekoperation.md) | "." |
| [KS_LogicalMemoryType enumeration](ne-ksproxy-ks_logicalmemorytype.md) | "." |
| [PIPE_ALLOCATOR_PLACE enumeration](ne-ksproxy-pipe_allocator_place.md) | "." |
| [PIPE_STATE enumeration](ne-ksproxy-pipe_state.md) | "." |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IKsAggregateControl interface](nn-ksproxy-iksaggregatecontrol.md) | The IKsAggregateControl interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface. |
| [IKsAllocator interface](nn-ksproxy-iksallocator.md) | TheIKsAllocator interface provides methods that control and query an allocator. IKsAllocator is for proxy use and not recommended for application use. |
| [IKsAllocatorEx interface](nn-ksproxy-iksallocatorex.md) | The IKsAllocatorEx interface is for proxy use and not recommended for application use. IKsAllocatorEx inherits all the methods of the IKsAllocator interface and extends IKsAllocator to provide methods that further control and query an allocator. |
| [IKsClockPropertySet interface](nn-ksproxy-iksclockpropertyset.md) | The IKsClockPropertySet interface provides methods that let the proxy accurately reflect time. |
| [IKsControl interface](nn-ksproxy-ikscontrol.md) | The IKsControl interface provides user-mode methods that control a KS filter or KS pin. See the IKsControl AVStream COM interface for information about the user-mode equivalent of this interface. |
| [IKsDataTypeCompletion interface](nn-ksproxy-iksdatatypecompletion.md) | The IKsDataTypeCompletion interface provides a method to complete partially specified media types that are passed to the IAMStreamConfig |
| [IKsDataTypeHandler interface](nn-ksproxy-iksdatatypehandler.md) | The IKsDataTypeHandler interface provides methods that perform optional preprocessing and postprocessing of media samples. |
| [IKsInterfaceHandler interface](nn-ksproxy-iksinterfacehandler.md) | The IKsInterfaceHandler interface provides methods that marshal samples into the kernel based on the KSPIN_INTERFACE structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler. |
| [IKsNotifyEvent interface](nn-ksproxy-iksnotifyevent.md) | The IKsNotifyEvent interface provides a method to cause the KS object that owns a DirectShow event to issue the event with the given parameters. |
| [IKsObject interface](nn-ksproxy-iksobject.md) | The IKsObject interface provides a method to retrieve the file handle of a KS object. |
| [IKsPin interface](nn-ksproxy-ikspin.md) | The IKsPin interface provides methods that control and retrieve information about a pin. |
| [IKsPinEx interface](nn-ksproxy-ikspinex.md) | The IKsPinEx interface inherits all the methods of the IKsPin interface and extends IKsPin to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt. |
| [IKsPinFactory interface](nn-ksproxy-ikspinfactory.md) | The IKsPinFactory interface provides a method that retrieves the identifier of a pin factory. |
| [IKsPinPipe interface](nn-ksproxy-ikspinpipe.md) | The IKsPinPipe interface is for proxy use and not recommended for application use. IKsPinPipe provides methods that control a pin pipe. |
| [IKsPropertySet interface](nn-ksproxy-ikspropertyset.md) | The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver. |
| [IKsQualityForwarder interface](nn-ksproxy-iksqualityforwarder.md) | The IKsQualityForwarder interface inherits the method of the IKsObject interface and extends IKsObject to provide a method that flushes information from a pin. |
| [IKsTopology interface](nn-ksproxy-ikstopology.md) | The IKsTopology interface provides a method that opens topology node objects contained within a filter. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IKsAggregateControl::KsAddAggregate method](nf-ksproxy-iksaggregatecontrol-ksaddaggregate.md) | The KsAddAggregate method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the IKsAggregateControl interface. |
| [IKsAggregateControl::KsRemoveAggregate method](nf-ksproxy-iksaggregatecontrol-ksremoveaggregate.md) | The KsRemoveAggregate method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the IKsAggregateControl interface. |
| [IKsAllocator::KsGetAllocatorHandle method](nf-ksproxy-iksallocator-ksgetallocatorhandle.md) | Retrieves a file handle to an allocator. |
| [IKsAllocator::KsGetAllocatorMode method](nf-ksproxy-iksallocator-ksgetallocatormode.md) | Returns the mode in which an allocator allocates memory. |
| [IKsAllocator::KsGetAllocatorStatus method](nf-ksproxy-iksallocator-ksgetallocatorstatus.md) | Retrieves the status of an allocator. |
| [IKsAllocator::KsSetAllocatorMode method](nf-ksproxy-iksallocator-kssetallocatormode.md) | Sets the mode in which an allocator allocates memory. |
| [IKsAllocatorEx::KsGetProperties method](nf-ksproxy-iksallocatorex-ksgetproperties.md) | Returns the properties for an allocator. |
| [IKsAllocatorEx::KsSetAllocatorHandle method](nf-ksproxy-iksallocatorex-kssetallocatorhandle.md) | Sets the handle for an allocator. |
| [IKsAllocatorEx::KsSetProperties method](nf-ksproxy-iksallocatorex-kssetproperties.md) | Sets the properties for an allocator. |
| [IKsClockPropertySet::KsGetCorrelatedPhysicalTime method](nf-ksproxy-iksclockpropertyset-ksgetcorrelatedphysicaltime.md) | The KsGetCorrelatedPhysicalTime method retrieves the physical time and the correlated system time from the underlying clock. |
| [IKsClockPropertySet::KsGetCorrelatedTime method](nf-ksproxy-iksclockpropertyset-ksgetcorrelatedtime.md) | The KsGetCorrelatedTime method retrieves the current time and the correlated system time from the underlying clock. |
| [IKsClockPropertySet::KsGetPhysicalTime method](nf-ksproxy-iksclockpropertyset-ksgetphysicaltime.md) | The KsGetPhysicalTime method retrieves the physical time from the underlying clock. |
| [IKsClockPropertySet::KsGetResolution method](nf-ksproxy-iksclockpropertyset-ksgetresolution.md) | The KsGetResolution method retrieves the clock resolution from the underlying clock. |
| [IKsClockPropertySet::KsGetState method](nf-ksproxy-iksclockpropertyset-ksgetstate.md) | The KsGetState method retrieves the streaming state of a pin from the underlying clock. |
| [IKsClockPropertySet::KsGetTime method](nf-ksproxy-iksclockpropertyset-ksgettime.md) | The KsGetTime method retrieves the time of the underlying clock. |
| [IKsClockPropertySet::KsSetCorrelatedPhysicalTime method](nf-ksproxy-iksclockpropertyset-kssetcorrelatedphysicaltime.md) | The KsSetCorrelatedPhysicalTime method sets the physical time with the correlated system time on the underlying clock. |
| [IKsClockPropertySet::KsSetCorrelatedTime method](nf-ksproxy-iksclockpropertyset-kssetcorrelatedtime.md) | The KsSetCorrelatedTime method sets the current time with the correlated system time on the underlying clock. |
| [IKsClockPropertySet::KsSetPhysicalTime method](nf-ksproxy-iksclockpropertyset-kssetphysicaltime.md) | The KsSetPhysicalTime method sets the physical time on the underlying clock. |
| [IKsClockPropertySet::KsSetTime method](nf-ksproxy-iksclockpropertyset-kssettime.md) | The KsSetTime method sets the current time on the underlying clock. |
| [IKsControl::KsEvent method](nf-ksproxy-ikscontrol-ksevent.md) | The KsEvent method enables or disables an event, along with any other defined support operations available on an event set. |
| [IKsControl::KsMethod method](nf-ksproxy-ikscontrol-ksmethod.md) | The KsMethod method sends a method to a KS object, along with any other defined support operations available on a method set. |
| [IKsControl::KsProperty method](nf-ksproxy-ikscontrol-ksproperty.md) | The KsProperty method sets a property or retrieves property information, along with any other defined support operations available on a property set. |
| [IKsDataTypeCompletion::KsCompleteMediaType method](nf-ksproxy-iksdatatypecompletion-kscompletemediatype.md) | The KsCompleteMediaType method completes a partially-specified media type that was first presented to the IAMStreamConfig |
| [IKsDataTypeHandler::KsCompleteIoOperation method](nf-ksproxy-iksdatatypehandler-kscompleteiooperation.md) | The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation. |
| [IKsDataTypeHandler::KsIsMediaTypeInRanges method](nf-ksproxy-iksdatatypehandler-ksismediatypeinranges.md) | The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges. |
| [IKsDataTypeHandler::KsPrepareIoOperation method](nf-ksproxy-iksdatatypehandler-ksprepareiooperation.md) | The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation. |
| [IKsDataTypeHandler::KsQueryExtendedSize method](nf-ksproxy-iksdatatypehandler-ksqueryextendedsize.md) | The KsQueryExtendedSize method retrieves extended header information required for input and output (I/O) operations. |
| [IKsDataTypeHandler::KsSetMediaType method](nf-ksproxy-iksdatatypehandler-kssetmediatype.md) | The KsSetMediaType method sets the media type for a data type handler. |
| [IKsInterfaceHandler::KsCompleteIo method](nf-ksproxy-iksinterfacehandler-kscompleteio.md) | The KsCompleteIo method cleans up extended headers and releases media samples after input and output (I/O) complete. |
| [IKsInterfaceHandler::KsProcessMediaSamples method](nf-ksproxy-iksinterfacehandler-ksprocessmediasamples.md) | The KsProcessMediaSamples method processes media samples. |
| [IKsInterfaceHandler::KsSetPin method](nf-ksproxy-iksinterfacehandler-kssetpin.md) | The KsSetPin method informs the streaming interface handler about the pin with which to communicate when passing data. |
| [IKsNotifyEvent::KsNotifyEvent method](nf-ksproxy-iksnotifyevent-ksnotifyevent.md) | The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs. |
| [IKsObject::KsGetObjectHandle method](nf-ksproxy-iksobject-ksgetobjecthandle.md) | The KsGetObjectHandle method retrieves a file handle to a KS object. |
| [IKsPin::KsCreateSinkPinHandle method](nf-ksproxy-ikspin-kscreatesinkpinhandle.md) | The KsCreateSinkPinHandle method creates a pin handle and stores it in the KS pin object. |
| [IKsPin::KsDecrementPendingIoCount method](nf-ksproxy-ikspin-ksdecrementpendingiocount.md) | The KsDecrementPendingIoCount method decrements the number of input/output (I/O) operations that are in progress on a pin. |
| [IKsPin::KsDeliver method](nf-ksproxy-ikspin-ksdeliver.md) | The KsDeliver method delivers a media sample from an output pin to an input pin, continues an I/O operation by retrieving the next buffer from an allocator, and submits the buffer to the associated device. |
| [IKsPin::KsGetCurrentCommunication method](nf-ksproxy-ikspin-ksgetcurrentcommunication.md) | The KsGetCurrentCommunication method retrieves the current communication direction, interface, and medium of a pin. |
| [IKsPin::KsIncrementPendingIoCount method](nf-ksproxy-ikspin-ksincrementpendingiocount.md) | The KsIncrementPendingIoCount method increments the number of input/output (I/O) operations that are in progress on a pin. |
| [IKsPin::KsMediaSamplesCompleted method](nf-ksproxy-ikspin-ksmediasamplescompleted.md) | The KsMediaSamplesCompleted method informs a pin that a stream segment completed. |
| [IKsPin::KsPeekAllocator method](nf-ksproxy-ikspin-kspeekallocator.md) | The KsPeekAllocator method returns a pointer to an IMemAllocator interface for a pin's assigned allocator. |
| [IKsPin::KsPropagateAcquire method](nf-ksproxy-ikspin-kspropagateacquire.md) | The KsPropagateAcquire method directs all the pins on the filter to attain the Acquire state. |
| [IKsPin::KsQueryInterfaces method](nf-ksproxy-ikspin-ksqueryinterfaces.md) | The KsQueryInterfaces method retrieves interfaces that a pin supports. |
| [IKsPin::KsQueryMediums method](nf-ksproxy-ikspin-ksquerymediums.md) | The KsQueryMediums method retrieves mediums that a pin supports. |
| [IKsPinEx::KsNotifyError method](nf-ksproxy-ikspinex-ksnotifyerror.md) | The KsNotifyError method notifies the filter graph of an error to give the filter graph an opportunity to halt. |
| [IKsPinFactory::KsPinFactory method](nf-ksproxy-ikspinfactory-kspinfactory.md) | The KsPinFactory method retrieves the identifier of a pin factory. |
| [IKsPinPipe::KsGetConnectedPin method](nf-ksproxy-ikspinpipe-ksgetconnectedpin.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetFilterName method](nf-ksproxy-ikspinpipe-ksgetfiltername.md) | Returns the name of a filter. |
| [IKsPinPipe::KsGetPinBusCache method](nf-ksproxy-ikspinpipe-ksgetpinbuscache.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPinFramingCache method](nf-ksproxy-ikspinpipe-ksgetpinframingcache.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPinName method](nf-ksproxy-ikspinpipe-ksgetpinname.md) | Returns the name of a pin. |
| [IKsPinPipe::KsGetPipe method](nf-ksproxy-ikspinpipe-ksgetpipe.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPipeAllocatorFlag method](nf-ksproxy-ikspinpipe-ksgetpipeallocatorflag.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPinBusCache method](nf-ksproxy-ikspinpipe-kssetpinbuscache.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPinFramingCache method](nf-ksproxy-ikspinpipe-kssetpinframingcache.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPipe method](nf-ksproxy-ikspinpipe-kssetpipe.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPipeAllocatorFlag method](nf-ksproxy-ikspinpipe-kssetpipeallocatorflag.md) | Not recommended for application use. |
| [IKsPropertySet::Get method](nf-ksproxy-ikspropertyset-get.md) | The Get method retrieves a property identified by a property-set GUID and a property identifier. |
| [IKsPropertySet::QuerySupported method](nf-ksproxy-ikspropertyset-querysupported.md) | The QuerySupported method determines whether a KS object supports a property set and the type of that support. |
| [IKsPropertySet::Set method](nf-ksproxy-ikspropertyset-set.md) | The Set method sets a property identified by a property-set GUID and a property identifier. |
| [IKsQualityForwarder::KsFlushClient method](nf-ksproxy-iksqualityforwarder-ksflushclient.md) | The KsFlushClient method flushes information from a pin. |
| [IKsTopology::CreateNodeInstance method](nf-ksproxy-ikstopology-createnodeinstance.md) | The CreateNodeInstance method requests a KS filter object to open a topology node object. |
