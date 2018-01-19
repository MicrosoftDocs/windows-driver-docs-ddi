---
UID: TP:stream
ms.assetid: 955ea1c2-d8bc-36d6-8195-eadc9d53b016
ms.author: windowsdriverdev
ms.date: 01/18/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Streaming media devices


Overview of the Streaming media devices technology.

To develop Streaming media devices, you need these headers:

 * [avc.h](..\avc\index.md)
 * [avcstrm.h](..\avcstrm\index.md)
 * [bdamedia.h](..\bdamedia\index.md)
 * [bdasup.h](..\bdasup\index.md)
 * [bdatypes.h](..\bdatypes\index.md)
 * [dsound.h](..\dsound\index.md)
 * [kcom.h](..\kcom\index.md)
 * [ks.h](..\ks\index.md)
 * [ksi.h](..\ksi\index.md)
 * [ksmedia.h](..\ksmedia\index.md)
 * [ksproxy.h](..\ksproxy\index.md)
 * [lamp.h](..\lamp\index.md)
 * [msviddrv.h](..\msviddrv\index.md)
 * [strmini.h](..\strmini\index.md)
 * [swenum.h](..\swenum\index.md)
 * [usbcamdi.h](..\usbcamdi\index.md)

For the programming guide, see [Streaming media devices](https://docs.microsoft.com/en-us/windows-hardware/drivers/stream).

## Functions

| Title   | Description   |
| ---- |:---- |
| [BdaCheckChanges function](..\bdasup\nf-bdasup-bdacheckchanges.md) | The BdaCheckChanges function verifies a new set of BDA topology changes before they are committed. |
| [BdaCommitChanges function](..\bdasup\nf-bdasup-bdacommitchanges.md) | The BdaCommitChanges function commits the changes to BDA topology that have occurred since the last call to the BdaStartChanges function. |
| [BdaCreateFilterFactory function](..\bdasup\nf-bdasup-bdacreatefilterfactory.md) | The BdaCreateFilterFactory function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology. |
| [BdaCreateFilterFactoryEx function](..\bdasup\nf-bdasup-bdacreatefilterfactoryex.md) | The BdaCreateFilterFactoryEx function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology. |
| [BdaCreatePin function](..\bdasup\nf-bdasup-bdacreatepin.md) | The BdaCreatePin function creates a new pin in the specified filter. |
| [BdaCreateTopology function](..\bdasup\nf-bdasup-bdacreatetopology.md) | The BdaCreateTopology function creates the topology between two pins. |
| [BdaDeletePin function](..\bdasup\nf-bdasup-bdadeletepin.md) | The BdaDeletePin function deletes a pin from the specified filter. |
| [BdaFilterFactoryUpdateCacheData function](..\bdasup\nf-bdasup-bdafilterfactoryupdatecachedata.md) | The BdaFilterFactoryUpdateCacheData function updates the pin data cache for an instance of a filter. |
| [BdaGetChangeState function](..\bdasup\nf-bdasup-bdagetchangestate.md) | The BdaGetChangeState function returns the current change state of BDA topology. |
| [BdaInitFilter function](..\bdasup\nf-bdasup-bdainitfilter.md) | The BdaInitFilter function initializes the BDA filter context associated with a filter instance. |
| [BdaMethodCreatePin function](..\bdasup\nf-bdasup-bdamethodcreatepin.md) | The BdaMethodCreatePin function creates a pin factory. |
| [BdaMethodCreateTopology function](..\bdasup\nf-bdasup-bdamethodcreatetopology.md) | The BdaMethodCreateTopology function creates a template topology between two pins of a filter. |
| [BdaMethodDeletePin function](..\bdasup\nf-bdasup-bdamethoddeletepin.md) | The BdaMethodDeletePin function deletes a pin factory. |
| [BdaPropertyGetControllingPinId function](..\bdasup\nf-bdasup-bdapropertygetcontrollingpinid.md) | The BdaPropertyGetControllingPinId function retrieves the identifier of a pin on which to control the properties, methods, and events of a specific node. |
| [BdaPropertyGetPinControl function](..\bdasup\nf-bdasup-bdapropertygetpincontrol.md) | The BdaPropertyGetPinControl function retrieves either the identifier or type of a pin. |
| [BdaPropertyNodeDescriptors function](..\bdasup\nf-bdasup-bdapropertynodedescriptors.md) | The BdaPropertyNodeDescriptors function retrieves a list of nodes in a template topology. |
| [BdaPropertyNodeEvents function](..\bdasup\nf-bdasup-bdapropertynodeevents.md) | The BdaPropertyNodeEvents function retrieves a list of events that a node supports. |
| [BdaPropertyNodeMethods function](..\bdasup\nf-bdasup-bdapropertynodemethods.md) | The BdaPropertyNodeMethods function retrieves a list of methods that a node supports. |
| [BdaPropertyNodeProperties function](..\bdasup\nf-bdasup-bdapropertynodeproperties.md) | The BdaPropertyNodeProperties function retrieves a list of properties that a node supports. |
| [BdaPropertyNodeTypes function](..\bdasup\nf-bdasup-bdapropertynodetypes.md) | The BdaPropertyNodeTypes function retrieves a list of node types in a template topology. |
| [BdaPropertyPinTypes function](..\bdasup\nf-bdasup-bdapropertypintypes.md) | The BdaPropertyPinTypes function retrieves a list of pin types in a template topology. |
| [BdaPropertyTemplateConnections function](..\bdasup\nf-bdasup-bdapropertytemplateconnections.md) | The BdaPropertyTemplateConnections function retrieves a list of connections that describe how pin types and node types are connected in a template topology. |
| [BdaStartChanges function](..\bdasup\nf-bdasup-bdastartchanges.md) | The BdaStartChanges function initiates the setting of new BDA topology changes. |
| [BdaUninitFilter function](..\bdasup\nf-bdasup-bdauninitfilter.md) | The BdaUninitFilter function removes the BDA filter context from the associated filter instance. |
| [BdaValidateNodeProperty function](..\bdasup\nf-bdasup-bdavalidatenodeproperty.md) | The BdaValidateNodeProperty function validates that a node property request is associated with a specific pin. |
| [KoCreateInstance function](..\kcom\nf-kcom-kocreateinstance.md) | The KoCreateInstance function creates an object of the class with the specified CLSID. |
| [KoDeviceInitialize function](..\kcom\nf-kcom-kodeviceinitialize.md) | The KoDeviceInitialize function adds a kernel COM create-item entry to the specified device object. |
| [KoDriverInitialize function](..\kcom\nf-kcom-kodriverinitialize.md) | The KoDriverInitialize function initializes a driver object to handle the kernel streaming interface. |
| [KoRelease function](..\kcom\nf-kcom-korelease.md) | The KoRelease function decrements the reference count for the calling interface on an object. |
| [KsAcquireCachedMdl function](..\ks\nf-ks-ksacquirecachedmdl.md) | This function is used to acquire the MDL cached by the KS port driver. The function is used by a kernel mode driver to acquire the MDL for a pipeline-supplied sample generated by an Avstream driver. |
| [KsAcquireControl function](..\ks\nf-ks-ksacquirecontrol.md) | The KsAcquireControl function acquires the filter control mutex for Object. |
| [KsAcquireDevice function](..\ks\nf-ks-ksacquiredevice.md) | The KsAcquireDevice function gains synchronous access for Device by acquiring the device mutex. |
| [KsAcquireDeviceSecurityLock function](..\ks\nf-ks-ksacquiredevicesecuritylock.md) | The KsAcquireDeviceSecurityLock function acquires the security lock associated with a device object. |
| [KsAcquireResetValue function](..\ks\nf-ks-ksacquireresetvalue.md) | The KsAcquireResetValue function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP. |
| [KsAddDevice function](..\ks\nf-ks-ksadddevice.md) | The KsAddDevice function is the default AddDevice handler installed by KsInitializeDriver. |
| [KsAddEvent function](..\ks\nf-ks-ksaddevent.md) | The KsAddEvent function adds an event to Object's event list. |
| [KsAddIrpToCancelableQueue function](..\ks\nf-ks-ksaddirptocancelablequeue.md) | The KsAddIrpToCancelableQueue function adds an IRP to a queue of cancelable IRPs, thus allowing the IRP to be canceled. If the IRP had been previously set to a canceled state, the KsAddIrpToCancelableQueue function completes the canceling of that IRP. |
| [KsAddItemToObjectBag function](..\ks\nf-ks-ksadditemtoobjectbag.md) | The KsAddItemToObjectBag function adds an object or block of memory to the given object bag. |
| [KsAddObjectCreateItemToDeviceHeader function](..\ks\nf-ks-ksaddobjectcreateitemtodeviceheader.md) | The KsAddObjectCreateItemToDeviceHeader function adds the specified create-item to an empty item in the previously allocated create item list for this device header. |
| [KsAddObjectCreateItemToObjectHeader function](..\ks\nf-ks-ksaddobjectcreateitemtoobjectheader.md) | The KsAddObjectCreateItemToObjectHeader function adds the specified create-item to an empty item in the previously allocated create item list for this object header. |
| [KsAllocateDefaultClock function](..\ks\nf-ks-ksallocatedefaultclock.md) | The KsAllocateDefaultClock function allocates and initializes the default clock structure. |
| [KsAllocateDefaultClockEx function](..\ks\nf-ks-ksallocatedefaultclockex.md) | The KsAllocateDefaultClockEx function allocates and initializes the default clock structure. |
| [KsAllocateDeviceHeader function](..\ks\nf-ks-ksallocatedeviceheader.md) | The KsAllocateDeviceHeader function allocates and initializes the required device extension header. |
| [KsAllocateExtraData function](..\ks\nf-ks-ksallocateextradata.md) | The KsAllocateExtraData function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller. |
| [KsAllocateObjectBag function](..\ks\nf-ks-ksallocateobjectbag.md) | The KsAllocateObjectBag function creates an object bag and associates it with a KSDEVICE. |
| [KsAllocateObjectCreateItem function](..\ks\nf-ks-ksallocateobjectcreateitem.md) | The KsAllocateObjectCreateItem function allocates a slot for the specified create item, optionally allocating space for and copying the create item data as well. |
| [KsAllocateObjectHeader function](..\ks\nf-ks-ksallocateobjectheader.md) | The KsAllocateObjectHeader function initializes the required file context header. |
| [KsCacheMedium function](..\ks\nf-ks-kscachemedium.md) | The KsCacheMedium function improves graph building performance of pins that use Mediums to define connectivity. |
| [KsCancelIo function](..\ks\nf-ks-kscancelio.md) | The KsCancelIo function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower. |
| [KsCompletePendingRequest function](..\ks\nf-ks-kscompletependingrequest.md) | The KsCompletePendingRequest function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING. |
| [KsCopyObjectBagItems function](..\ks\nf-ks-kscopyobjectbagitems.md) | The KsCopyObjectBagItems function copies all items from one object bag into another. |
| [KsCreateAllocator function](..\ks\nf-ks-kscreateallocator.md) | The KsCreateAllocator function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP. |
| [KsCreateAllocator2 function](..\ks\nf-ks-kscreateallocator2.md) | Creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP. |
| [KsCreateBusEnumObject function](..\swenum\nf-swenum-kscreatebusenumobject.md) | The KsCreateBusEnumObject function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services. |
| [KsCreateClock function](..\ks\nf-ks-kscreateclock.md) | The KsCreateClock function creates a handle to a clock instance. |
| [KsCreateClock2 function](..\ks\nf-ks-kscreateclock2.md) | Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized. |
| [KsCreateDefaultAllocator function](..\ks\nf-ks-kscreatedefaultallocator.md) | Given a validated IRP_MJ_CREATE request, the KsCreateDefaultAllocator function creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the allocator using an internal dispatch table (KSDISPATCH_TABLE). |
| [KsCreateDefaultAllocatorEx function](..\ks\nf-ks-kscreatedefaultallocatorex.md) | Creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(pIrp)-&gt;FileObject with this allocator using an internal dispatch table (KSDISPATCH_TABLE). |
| [KsCreateDefaultClock function](..\ks\nf-ks-kscreatedefaultclock.md) | Given an IRP_MJ_CREATE request, the KsCreateDefaultClock function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE). Does not complete the IRP or set the status in the IRP.The KsCreateDefaultClock function can only be called at PASSIVE_LEVEL. |
| [KsCreateDefaultSecurity function](..\ks\nf-ks-kscreatedefaultsecurity.md) | The KsCreateDefaultSecurity function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor. |
| [KsCreateDevice function](..\ks\nf-ks-kscreatedevice.md) | The KsCreateDevice function creates an AVStream device. |
| [KsCreateFilterFactory function](..\ks\nf-ks-kscreatefilterfactory.md) | The KsCreateFilterFactory function adds a filter factory to a given device. |
| [KsCreatePin function](..\ks\nf-ks-kscreatepin.md) | The KsCreatePin function passes a connection request to a device, creating a pin instance. This function can only be called at PASSIVE_LEVEL for kernel-mode clients. |
| [KsCreatePin2 function](..\ks\nf-ks-kscreatepin2.md) | Passes a connection request to a device, creating a pin instance. |
| [KsCreateTopologyNode function](..\ks\nf-ks-kscreatetopologynode.md) | The KsCreateTopologyNode function creates a handle to a topology node instance. The function can only be called at PASSIVE_LEVEL. |
| [KsCreateTopologyNode2 function](..\ks\nf-ks-kscreatetopologynode2.md) | Creates a handle to a topology node instance. |
| [KsDecrementCountedWorker function](..\ks\nf-ks-ksdecrementcountedworker.md) | Decrements the current worker count of a worker previous created by KsRegisterCountedWorker. This should be called after each task within a worker has been completed. |
| [KsDefaultAddEventHandler function](..\ks\nf-ks-ksdefaultaddeventhandler.md) | The KsDefaultAddEventHandler function is a default routine to handle event 'add' requests. |
| [KsDefaultDeviceIoCompletion function](..\ks\nf-ks-ksdefaultdeviceiocompletion.md) | The KsDefaultDeviceIoCompletion function is used to return a default response and to complete any device I/O control. |
| [KsDereferenceBusObject function](..\ks\nf-ks-ksdereferencebusobject.md) | Dereferences the bus Physical Device Object. |
| [KsDereferenceSoftwareBusObject function](..\swenum\nf-swenum-ksdereferencesoftwarebusobject.md) | The KsDereferenceSoftwareBusObject function decrements the reference count of the demand-load bus enumerator object's PDO. |
| [KsDeviceGetBusData function](..\ks\nf-ks-ksdevicegetbusdata.md) | The KsDeviceGetBusData function reads data from the bus where the given AVStream device resides. |
| [KsDeviceGetFirstChildFilterFactory function](..\ks\nf-ks-ksdevicegetfirstchildfilterfactory.md) | The KsDeviceGetFirstChildFilterFactory function returns the first child filter factory belonging to a given AVStream device. |
| [KsDeviceGetOuterUnknown function](..\ks\nf-ks-ksdevicegetouterunknown.md) | The KsDeviceGetOuterUnknown function returns the outer IUnknown of the AVStream device specified by Device. |
| [KsDeviceRegisterAdapterObject function](..\ks\nf-ks-ksdeviceregisteradapterobject.md) | The KsDeviceRegisterAdapterObject function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use IKsDeviceFunctions |
| [KsDeviceRegisterAggregatedClientUnknown function](..\ks\nf-ks-ksdeviceregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsDeviceRegisterThermalDispatch function](..\ks\nf-ks-ksdeviceregisterthermaldispatch.md) | This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver. |
| [KsDeviceSetBusData function](..\ks\nf-ks-ksdevicesetbusdata.md) | The KsDeviceSetBusData function writes data to the bus on which the specified AVStream device resides. |
| [KsDisableEvent function](..\ks\nf-ks-ksdisableevent.md) | The KsDisableEvent function disables events requested through IOCTL_KS_DISABLE_EVENT. |
| [KsDiscardEvent function](..\ks\nf-ks-ksdiscardevent.md) | The KsDiscardEvent function discards the memory used by an event entry after the objects have been dereferenced. |
| [KsDispatchFastIoDeviceControlFailure function](..\ks\nf-ks-ksdispatchfastiodevicecontrolfailure.md) | The KsDispatchFastIoDeviceControlFailure function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return FALSE. |
| [KsDispatchFastReadFailure function](..\ks\nf-ks-ksdispatchfastreadfailure.md) | The KsDispatchFastReadFailure function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return FALSE. |
| [KsDispatchInvalidDeviceRequest function](..\ks\nf-ks-ksdispatchinvaliddevicerequest.md) | The KsDispatchInvalidDeviceRequest function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST. |
| [KsDispatchIrp function](..\ks\nf-ks-ksdispatchirp.md) | KsDispatchIrp calls a dispatch routine corresponding to the function code of the specified IRP. KsDispatchIrp then returns the status code from this call. |
| [KsDispatchQuerySecurity function](..\ks\nf-ks-ksdispatchquerysecurity.md) | The KsDispatchQuerySecurity function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor. |
| [KsDispatchSetSecurity function](..\ks\nf-ks-ksdispatchsetsecurity.md) | The KsDispatchSetSecurity function is used in the KSDISPATCH_TABLE.SetSecurity entry to handle setting the current security descriptor. |
| [KsDispatchSpecificMethod function](..\ks\nf-ks-ksdispatchspecificmethod.md) | The KsDispatchSpecificMethod function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the KsMethodHandler function. The function can only be called at PASSIVE_LEVEL. |
| [KsDispatchSpecificProperty function](..\ks\nf-ks-ksdispatchspecificproperty.md) | The KsDispatchSpecificProperty function dispatches the property to a specific handler. |
| [KsEnableEvent function](..\ks\nf-ks-ksenableevent.md) | The KsEnableEvent function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL. |
| [KsEnableEventWithAllocator function](..\ks\nf-ks-ksenableeventwithallocator.md) | The KsEnableEventWithAllocator function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KsFastMethodHandler function](..\ks\nf-ks-ksfastmethodhandler.md) | The KsFastMethodHandler function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL. |
| [KsFastPropertyHandler function](..\ks\nf-ks-ksfastpropertyhandler.md) | The KsFastPropertyHandler function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL. |
| [KsFilterAcquireControl function](..\ks\nf-ks-ksfilteracquirecontrol.md) | The KsFilterAcquireControl function acquires the filter control mutex for the AVStream filter specified by Filter. |
| [KsFilterAcquireProcessingMutex function](..\ks\nf-ks-ksfilteracquireprocessingmutex.md) | The KsFilterAcquireProcessingMutex function acquires the processing mutex for a specified AVStream filter. |
| [KsFilterAddEvent function](..\ks\nf-ks-ksfilteraddevent.md) | The KsFilterAddEvent function adds an event to Filter's event list. |
| [KsFilterAddTopologyConnections function](..\ks\nf-ks-ksfilteraddtopologyconnections.md) | The KsFilterAddTopologyConnections function adds new topology connections to a filter. |
| [KsFilterAttemptProcessing function](..\ks\nf-ks-ksfilterattemptprocessing.md) | The KsFilterAttemptProcessing function attempts to initiate processing on Filter. |
| [KsFilterCreateNode function](..\ks\nf-ks-ksfiltercreatenode.md) | The KsFilterCreateNode function creates a new topology node on the specified filter. |
| [KsFilterCreatePinFactory function](..\ks\nf-ks-ksfiltercreatepinfactory.md) | The KsFilterCreatePinFactory function creates a new pin factory on the specified filter. |
| [KsFilterFactoryAddCreateItem function](..\ks\nf-ks-ksfilterfactoryaddcreateitem.md) | The KsFilterFactoryAddCreateItem function adds a new create item for the specified filter factory. |
| [KsFilterFactoryGetDevice function](..\ks\nf-ks-ksfilterfactorygetdevice.md) | The KsFilterFactoryGetDevice function returns the AVStream device to which FilterFactory belongs. |
| [KsFilterFactoryGetFirstChildFilter function](..\ks\nf-ks-ksfilterfactorygetfirstchildfilter.md) | The KsFilterFactoryGetFirstChildFilter function returns the first instantiated filter created by FilterFactory. |
| [KsFilterFactoryGetNextSiblingFilterFactory function](..\ks\nf-ks-ksfilterfactorygetnextsiblingfilterfactory.md) | The KsFilterFactoryGetNextSiblingFilterFactory function returns the next filter factory belonging to the parent device of FilterFactory. |
| [KsFilterFactoryGetOuterUnknown function](..\ks\nf-ks-ksfilterfactorygetouterunknown.md) | The KsFilterFactoryGetOuterUnknown function returns the outer IUnknown of the specified filter factory. |
| [KsFilterFactoryGetParentDevice function](..\ks\nf-ks-ksfilterfactorygetparentdevice.md) | The KsFilterFactoryGetParentDevice function returns the parent device of the given filter factory. |
| [KsFilterFactoryGetSymbolicLink function](..\ks\nf-ks-ksfilterfactorygetsymboliclink.md) | The KsFilterFactoryGetSymbolicLink function returns the symbolic link associated with a given filter factory. |
| [KsFilterFactoryRegisterAggregatedClientUnknown function](..\ks\nf-ks-ksfilterfactoryregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsFilterFactorySetDeviceClassesState function](..\ks\nf-ks-ksfilterfactorysetdeviceclassesstate.md) | The KsFilterFactorySetDeviceClassesState function enables or disables the device classes that have been registered by a given filter factory. |
| [KsFilterFactoryUpdateCacheData function](..\ks\nf-ks-ksfilterfactoryupdatecachedata.md) | The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory. |
| [KsFilterGenerateEvents function](..\ks\nf-ks-ksfiltergenerateevents.md) | The KsFilterGenerateEvents function generates events of an indicated type that are present in Filter's event list. |
| [KsFilterGetAndGate function](..\ks\nf-ks-ksfiltergetandgate.md) | The KsFilterGetAndGate function returns Filter's AND gate. |
| [KsFilterGetChildPinCount function](..\ks\nf-ks-ksfiltergetchildpincount.md) | The KsFilterGetChildPinCountfunctionreturns the number of pins of a given type that are currently instantiated on a given filter. |
| [KsFilterGetDevice function](..\ks\nf-ks-ksfiltergetdevice.md) | The KsFilterGetDevice function returns the AVStream device to which Filter belongs. |
| [KsFilterGetFirstChildPin function](..\ks\nf-ks-ksfiltergetfirstchildpin.md) | The KsFilterGetFirstChildPin function returns the first instantiated pin of type PinID on the filter specified by Filter. |
| [KsFilterGetNextSiblingFilter function](..\ks\nf-ks-ksfiltergetnextsiblingfilter.md) | The KsFilterGetNextSiblingFilter function returns the next instantiated filter belonging to the parent filter factory of Filter. |
| [KsFilterGetOuterUnknown function](..\ks\nf-ks-ksfiltergetouterunknown.md) | The KsFilterGetOuterUnknown function returns the outer IUnknown interface of the filter specified by Filter. |
| [KsFilterGetParentFilterFactory function](..\ks\nf-ks-ksfiltergetparentfilterfactory.md) | The KsFilterGetParentFilterFactory function returns the parent filter factory of the given filter. |
| [KsFilterRegisterAggregatedClientUnknown function](..\ks\nf-ks-ksfilterregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsFilterRegisterPowerCallbacks function](..\ks\nf-ks-ksfilterregisterpowercallbacks.md) | The KsFilterRegisterPowerCallbacks function registers power management callbacks for Filter. |
| [KsFilterReleaseControl function](..\ks\nf-ks-ksfilterreleasecontrol.md) | The KsFilterReleaseControl function releases the control mutex for the AVStream filter specified by Filter. |
| [KsFilterReleaseProcessingMutex function](..\ks\nf-ks-ksfilterreleaseprocessingmutex.md) | The KsFilterReleaseProcessingMutex function releases the processing mutex for the AVStream filter specified by Filter. |
| [KsForwardAndCatchIrp function](..\ks\nf-ks-ksforwardandcatchirp.md) | The KsForwardAndCatchIrp function forwards an IRP to the specified driver after initializing the next stack location, and regains control of the IRP on completion from that driver. |
| [KsForwardIrp function](..\ks\nf-ks-ksforwardirp.md) | The KsForwardIrp function forwards an IRP to the specified driver after initializing the next stack location and setting the file object. |
| [KsFreeDefaultClock function](..\ks\nf-ks-ksfreedefaultclock.md) | The KsFreeDefaultClock function frees a default clock structure previously allocated with KsAllocateDefaultClock, taking into account any currently running timer DPCs. |
| [KsFreeDeviceHeader function](..\ks\nf-ks-ksfreedeviceheader.md) | The KsFreeDeviceHeader function cleans up and frees a previously allocated device header. |
| [KsFreeEventList function](..\ks\nf-ks-ksfreeeventlist.md) | The KsFreeEventList function handles freeing all events from a specified list, with the assumption that these events are composed of KSEVENT_ENTRY structures. This function can only be called at PASSIVE_LEVEL. |
| [KsFreeObjectBag function](..\ks\nf-ks-ksfreeobjectbag.md) | The KsFreeObjectBag function empties and frees an object bag. |
| [KsFreeObjectCreateItem function](..\ks\nf-ks-ksfreeobjectcreateitem.md) | Frees the slot for the specified create item. |
| [KsFreeObjectCreateItemsByContext function](..\ks\nf-ks-ksfreeobjectcreateitemsbycontext.md) | Frees all create items with a specific context. |
| [KsFreeObjectHeader function](..\ks\nf-ks-ksfreeobjectheader.md) | The KsFreeObjectHeader function cleans up and frees a previously allocated object header. |
| [KsGateAddOffInputToAnd function](..\ks\nf-ks-ksgateaddoffinputtoand.md) | The KsGateAddOffInputToAnd function adds a new input in the OFF state to a given AND gate. |
| [KsGateAddOffInputToOr function](..\ks\nf-ks-ksgateaddoffinputtoor.md) | The KsGateAddOffInputToOr function adds a new input in the OFF state to a given OR gate. |
| [KsGateAddOnInputToAnd function](..\ks\nf-ks-ksgateaddoninputtoand.md) | The KsGateAddOnInputToAnd function adds a new input in the ON state to a given AND gate. |
| [KsGateAddOnInputToOr function](..\ks\nf-ks-ksgateaddoninputtoor.md) | The KsGateAddOnInputToOr function adds a new input in the ON state to a given OR gate. |
| [KsGateCaptureThreshold function](..\ks\nf-ks-ksgatecapturethreshold.md) | The KsGateCaptureThreshold function is used to capture an ON input of an AND gate specified by Gate. |
| [KsGateGetStateUnsafe function](..\ks\nf-ks-ksgategetstateunsafe.md) | The KsGateGetStateUnsafe function returns the state of the given gate (open or closed) in an unsafe manner, that is without regard to synchronization. |
| [KsGateInitialize function](..\ks\nf-ks-ksgateinitialize.md) | The KsGateInitialize function initializes a gate for use. |
| [KsGateInitializeAnd function](..\ks\nf-ks-ksgateinitializeand.md) | The KsGateInitializeAnd function initializes a KSGATE structure as an AND gate and attaches it to the OR gate specified by NextOrGate. |
| [KsGateInitializeOr function](..\ks\nf-ks-ksgateinitializeor.md) | The KsGateInitializeOr function initializes a KSGATE structure as an OR gate and attaches it to the AND gate specified by NextAndGate. |
| [KsGateRemoveOffInputFromAnd function](..\ks\nf-ks-ksgateremoveoffinputfromand.md) | The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate. |
| [KsGateRemoveOffInputFromOr function](..\ks\nf-ks-ksgateremoveoffinputfromor.md) | The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate. |
| [KsGateRemoveOnInputFromAnd function](..\ks\nf-ks-ksgateremoveoninputfromand.md) | The KsGateRemoveOnInputFromAnd function removes an existing input that is in the ON state from an AND gate. |
| [KsGateRemoveOnInputFromOr function](..\ks\nf-ks-ksgateremoveoninputfromor.md) | The KsGateRemoveOnInputFromOr function removes an existing input that is in the ON state from an OR gate. |
| [KsGateTerminateAnd function](..\ks\nf-ks-ksgateterminateand.md) | The KsGateTerminateAnd function deletes an existing AND gate and removes an input from any attached OR gate. |
| [KsGateTerminateOr function](..\ks\nf-ks-ksgateterminateor.md) | The KsGateTerminateOr function deletes an existing OR gate and removes an input from any attached AND gate. |
| [KsGateTurnInputOff function](..\ks\nf-ks-ksgateturninputoff.md) | The KsGateTurnInputOff function turns off an existing input to Gate. |
| [KsGateTurnInputOn function](..\ks\nf-ks-ksgateturninputon.md) | The KsGateTurnInputOn function turns on an existing input to Gate. |
| [KsGenerateDataEvent function](..\ks\nf-ks-ksgeneratedataevent.md) | The KsGenerateDataEvent function generates one of the standard event notifications when given an event entry structure and callback data. |
| [KsGenerateEvent function](..\ks\nf-ks-ksgenerateevent.md) | The KsGenerateEvent function generates a standard event notification given an event entry structure. |
| [KsGenerateEventList function](..\ks\nf-ks-ksgenerateeventlist.md) | The KsGenerateEventList function enumerates the event list and searches for the specified event to generate. |
| [KsGenerateEvents function](..\ks\nf-ks-ksgenerateevents.md) | The KsGenerateEvents function generates events of an indicated type that are present in Object's event list. |
| [KsGenerateThermalEvent function](..\ks\nf-ks-ksgeneratethermalevent.md) | This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management. |
| [KsGetBusEnumIdentifier function](..\swenum\nf-swenum-ksgetbusenumidentifier.md) | The KsGetBusEnumIdentifier function retrieves the software bus enumerator identifier for the bus device associated with the given IRP. |
| [KsGetBusEnumParentFDOFromChildPDO function](..\swenum\nf-swenum-ksgetbusenumparentfdofromchildpdo.md) | The KsGetBusEnumParentFDOFromChildPDO function retrieves the FDO of the parent of the given child PDO. |
| [KsGetBusEnumPnpDeviceObject function](..\swenum\nf-swenum-ksgetbusenumpnpdeviceobject.md) | The KsGetBusEnumPnpDeviceObject function retrieves the Plug and Play device object attached to the given device object. |
| [KsGetDefaultClockState function](..\ks\nf-ks-ksgetdefaultclockstate.md) | The KsGetDefaultClockState function gets the current state of the clock.The function can be called at DISPATCH_LEVEL. |
| [KsGetDefaultClockTime function](..\ks\nf-ks-ksgetdefaultclocktime.md) | The KsGetDefaultClockTime function gets the current time of the clock.The function can be called at DISPATCH_LEVEL. |
| [KsGetDevice function](..\ks\nf-ks-ksgetdevice.md) | The KsGetDevice function returns the AVStream device structure to which Object belongs. |
| [KsGetDeviceForDeviceObject function](..\ks\nf-ks-ksgetdevicefordeviceobject.md) | The KsGetDeviceForDeviceObject function returns the AVStream device structure for a given functional device object. |
| [KsGetFilterFromFileObject function](..\ks\nf-ks-ksgetfilterfromfileobject.md) | The KsGetFilterFromFileObject function returns the AVStream filter object associated with FileObject. |
| [KsGetFilterFromIrp function](..\ks\nf-ks-ksgetfilterfromirp.md) | The KsGetFilterFromIrp function returns the AVStream filter object associated with a given IRP. |
| [KsGetFirstChild function](..\ks\nf-ks-ksgetfirstchild.md) | The KsGetFirstChild function returns the first AVStream child object of Object. |
| [KsGetImageNameAndResourceId function](..\ks\nf-ks-ksgetimagenameandresourceid.md) | The KsGetImageNameAndResourceId function returns the image name and resource identifier that corresponds to the RegKey handle. |
| [KsGetMediaType function](..\ksproxy\nf-ksproxy-ksgetmediatype.md) | The KsGetMediaType function retrieves information about a media type on a pin factory identifier. |
| [KsGetMediaTypeCount function](..\ksproxy\nf-ksproxy-ksgetmediatypecount.md) | The KsGetMediaTypeCount function returns the number of available media types on a pin factory identifier. |
| [KsGetMultiplePinFactoryItems function](..\ksproxy\nf-ksproxy-ksgetmultiplepinfactoryitems.md) | The KsGetMultiplePinFactoryItems function retrieves pin property items in a variable length data buffer. |
| [KsGetNextSibling function](..\ks\nf-ks-ksgetnextsibling.md) | The KsGetNextSibling function returns the next sibling of a given object. |
| [KsGetNodeIdFromIrp function](..\ks\nf-ks-ksgetnodeidfromirp.md) | The KsGetNodeIdFromIrp function returns the node ID of the node to which Irp was submitted. |
| [KsGetObjectFromFileObject function](..\ks\nf-ks-ksgetobjectfromfileobject.md) | The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject. |
| [KsGetObjectTypeFromFileObject function](..\ks\nf-ks-ksgetobjecttypefromfileobject.md) | The KsGetObjectTypeFromFileObject function returns the AVStream object type that is associated with a given file object. |
| [KsGetObjectTypeFromIrp function](..\ks\nf-ks-ksgetobjecttypefromirp.md) | The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP. |
| [KsGetOuterUnknown function](..\ks\nf-ks-ksgetouterunknown.md) | The KsGetOuterUnknown function returns the outer IUnknown of a given AVStream object. |
| [KsGetParent function](..\ks\nf-ks-ksgetparent.md) | The KsGetParent function acquires the parent of the given object. |
| [KsGetPinFromFileObject function](..\ks\nf-ks-ksgetpinfromfileobject.md) | The KsGetPinFromFileObject function returns the AVStream pin object associated with FileObject. |
| [KsGetPinFromIrp function](..\ks\nf-ks-ksgetpinfromirp.md) | The KsGetPinFromIrp function returns the AVStream pin object associated with the given IRP. |
| [KsHandleSizedListQuery function](..\ks\nf-ks-kshandlesizedlistquery.md) | The KsHandleSizedListQuery function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves. |
| [KsIncrementCountedWorker function](..\ks\nf-ks-ksincrementcountedworker.md) | Increments the current worker count, and optionally queues the counted work item with the worker previously created by KsRegisterCountedWorker. |
| [KsInitializeDevice function](..\ks\nf-ks-ksinitializedevice.md) | The KsInitializeDevice function is called by AVStream to initialize the AVStream device class from within KsCreateDevice. |
| [KsInitializeDeviceProfile function](..\ks\nf-ks-ksinitializedeviceprofile.md) | The KsInitializeDeviceProfile API must be called by all miniport drivers to initialize the profile store and publish the device profiles. |
| [KsInitializeDriver function](..\ks\nf-ks-ksinitializedriver.md) | The KsInitializeDriver function initializes the driver object of an AVStream minidriver. |
| [KsInstallBusEnumInterface function](..\swenum\nf-swenum-ksinstallbusenuminterface.md) | The KsInstallBusEnumInterface function installs an interface to the demand-load bus enumerator object. |
| [KsIsBusEnumChildDevice function](..\swenum\nf-swenum-ksisbusenumchilddevice.md) | The KsIsBusEnumChildDevice function determines if the given device object is a child device of the demand-load bus enumerator object. |
| [KsLoadResource function](..\ks\nf-ks-ksloadresource.md) | Copies (loads) a resource from the given image. |
| [KsMapModuleName function](..\ks\nf-ks-ksmapmodulename.md) | The KsMapModuleName function returns the image name and resource identifier that corresponds to the PhysicalDeviceObject and ModuleName parameters. |
| [KsMergeAutomationTables function](..\ks\nf-ks-ksmergeautomationtables.md) | The KsMergeAutomationTables function merges two automation tables. |
| [KsMethodHandler function](..\ks\nf-ks-ksmethodhandler.md) | The KsMethodHandler function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL. |
| [KsMethodHandlerWithAllocator function](..\ks\nf-ks-ksmethodhandlerwithallocator.md) | The KsMethodHandlerWithAllocator functions performs the same handling as KsMethodHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KsMoveIrpsOnCancelableQueue function](..\ks\nf-ks-ksmoveirpsoncancelablequeue.md) | The KsMoveIrpsOnCancelableQueue function moves the specified IRPs from the SourceList parameter to the DestinationList parameter depending on the value returned from the minidriver-defined KStrIrpListCallback function. |
| [KsNullDriverUnload function](..\ks\nf-ks-ksnulldriverunload.md) | The KsNullDriverUnload function is a default function a driver can use when it has no other tasks to do in its unload function, but must still allow the device to be unloaded by its presence. |
| [KsOpenDefaultDevice function](..\ksproxy\nf-ksproxy-ksopendefaultdevice.md) | The KsOpenDefaultDevice function opens a handle to the first device that is listed in the specified Plug and Play (PnP) category. |
| [KsPersistDeviceProfile function](..\ks\nf-ks-kspersistdeviceprofile.md) | The KsPersistDeviceProfile API commits the profile information to the persistent store. |
| [KsPinAcquireControl function](..\ks\nf-ks-kspinacquirecontrol.md) | The KsPinAcquireControl function acquires the control mutex for the AVStream pin specified by Pin. |
| [KsPinAcquireProcessingMutex function](..\ks\nf-ks-kspinacquireprocessingmutex.md) | The KsPinAcquireProcessingMutex function acquires the processing mutex for the AVStream pin specified by Pin. |
| [KsPinAddEvent function](..\ks\nf-ks-kspinaddevent.md) | The KsPinAddEvent function adds a specified event to Pin's event list. |
| [KsPinAttachAndGate function](..\ks\nf-ks-kspinattachandgate.md) | The KsPinAttachAndGate function connects Pin as an input to a previously initialized AND gate, and connects AndGate as an input to the relevant filter's AND gate. |
| [KsPinAttachOrGate function](..\ks\nf-ks-kspinattachorgate.md) | The KsPinAttachOrGate function connects Pin as an input to a previously initialized OR gate, and connects OrGate as an input to the relevant filter's AND gate. |
| [KsPinAttemptProcessing function](..\ks\nf-ks-kspinattemptprocessing.md) | The KsPinAttemptProcessing function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on Pin by sending a processing dispatch call to Pin's processing object. |
| [KsPinDataIntersection function](..\ks\nf-ks-kspindataintersection.md) | The KsPinDataIntersection function handles the KSPROPERTY_PIN_DATAINTERSECTION property through a callback function and performs much of the initial validation of the parameters that are passed. |
| [KsPinDataIntersectionEx function](..\ks\nf-ks-kspindataintersectionex.md) | The KsPinDataIntersectionEx function handles the KSPROPERTY_PIN_DATAINTERSECTION through a callback function. |
| [KsPinGenerateEvents function](..\ks\nf-ks-kspingenerateevents.md) | The KsPinGenerateEvents function generates events of an indicated type that are present in Pin's event list. |
| [KsPinGetAndGate function](..\ks\nf-ks-kspingetandgate.md) | The KsPinGetAndGate function returns the processing control gate for Pin. |
| [KsPinGetAvailableByteCount function](..\ks\nf-ks-kspingetavailablebytecount.md) | The KsPinGetAvailableByteCount routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin. |
| [KsPinGetConnectedFilterInterface function](..\ks\nf-ks-kspingetconnectedfilterinterface.md) | The KsPinGetConnectedFilterInterface function queries the filter to which Pin is connected in order to obtain a pointer to a COM interface. |
| [KsPinGetConnectedPinDeviceObject function](..\ks\nf-ks-kspingetconnectedpindeviceobject.md) | The KsPinGetConnectedPinDeviceObject function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin Pin. |
| [KsPinGetConnectedPinFileObject function](..\ks\nf-ks-kspingetconnectedpinfileobject.md) | The KsPinGetConnectedPinFileObject function returns the file object for the pin to which Pin is connected. Works only for source pins. |
| [KsPinGetConnectedPinInterface function](..\ks\nf-ks-kspingetconnectedpininterface.md) | The KsPinGetConnectedPinInterface function queries the pin to which Pin is connected for a COM style interface. |
| [KsPinGetCopyRelationships function](..\ks\nf-ks-kspingetcopyrelationships.md) | The KsPinGetCopyRelationships function returns copy relationship information for a pin that is contained within a pin-centric filter. |
| [KsPinGetDevice function](..\ks\nf-ks-kspingetdevice.md) | The KsPinGetDevice function returns the AVStream device to which Pin belongs. |
| [KsPinGetFirstCloneStreamPointer function](..\ks\nf-ks-kspingetfirstclonestreampointer.md) | The KsPinGetFirstCloneStreamPointer function returns the first cloned stream pointer on Pin. |
| [KsPinGetLeadingEdgeStreamPointer function](..\ks\nf-ks-kspingetleadingedgestreampointer.md) | The KsPinGetLeadingEdgeStreamPointer function acquires the leading edge stream pointer for the queue associated with the given pin. |
| [KsPinGetNextSiblingPin function](..\ks\nf-ks-kspingetnextsiblingpin.md) | The KsPinGetNextSiblingPin function returns the next instantiated pin of the same type and on the same filter as Pin. |
| [KsPinGetOuterUnknown function](..\ks\nf-ks-kspingetouterunknown.md) | The KsPinGetOuterUnknown function returns the outer IUnknown of the pin specified by Pin. |
| [KsPinGetParentFilter function](..\ks\nf-ks-kspingetparentfilter.md) | The KsPinGetParentFilter function returns the parent filter of Pin. |
| [KsPinGetReferenceClockInterface function](..\ks\nf-ks-kspingetreferenceclockinterface.md) | The KsPinGetReferenceClockInterface function returns a COM style interface to the reference clock associated with Pin. This interface pointer will be an IKsReferenceClock interface. |
| [KsPinGetTrailingEdgeStreamPointer function](..\ks\nf-ks-kspingettrailingedgestreampointer.md) | The KsPinGetTrailingEdgeStreamPointer function acquires the trailing edge stream pointer for the queue associated with the specified pin. |
| [KsPinHandshake function](..\ks\nf-ks-kspinhandshake.md) | The KsPinHandshake function attempts a protocol handshake with a connected pin. |
| [KsPinPropertyHandler function](..\ks\nf-ks-kspinpropertyhandler.md) | The KsPinPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Pin property set. This handling does not include KSPROPERTY_PIN_CINSTANCES or KSPROPERTY_PIN_DATAINTERSECTION. |
| [KsPinRegisterAggregatedClientUnknown function](..\ks\nf-ks-kspinregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsPinRegisterFrameReturnCallback function](..\ks\nf-ks-kspinregisterframereturncallback.md) | The KsPinRegisterFrameReturnCallback function registers a frame return callback with AVStream for a given pin. |
| [KsPinRegisterHandshakeCallback function](..\ks\nf-ks-kspinregisterhandshakecallback.md) | The KsPinRegisterHandshakeCallback function registers a minidriver-provided callback routine for a given pin. |
| [KsPinRegisterIrpCompletionCallback function](..\ks\nf-ks-kspinregisterirpcompletioncallback.md) | The KsPinRegisterIrpCompletionCallback function registers a minidriver-defined callback routine for a specified pin. |
| [KsPinRegisterPowerCallbacks function](..\ks\nf-ks-kspinregisterpowercallbacks.md) | The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin. |
| [KsPinReleaseControl function](..\ks\nf-ks-kspinreleasecontrol.md) | The KsPinReleaseControl function releases the control mutex for the AVStream pin specified by Pin. |
| [KsPinReleaseProcessingMutex function](..\ks\nf-ks-kspinreleaseprocessingmutex.md) | The KsPinReleaseProcessingMutex function releases the processing mutex for the AVStream pin specified by Pin. |
| [KsPinSetPinClockTime function](..\ks\nf-ks-kspinsetpinclocktime.md) | The KsPinSetPinClockTime function sets the current time on the clock exposed by Pin. |
| [KsPinSubmitFrame function](..\ks\nf-ks-kspinsubmitframe.md) | If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit. |
| [KsPinSubmitFrameMdl function](..\ks\nf-ks-kspinsubmitframemdl.md) | If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit. |
| [KsProbeStreamIrp function](..\ks\nf-ks-ksprobestreamirp.md) | The KsProbeStreamIrp function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header. |
| [KsProcessPinUpdate function](..\ks\nf-ks-ksprocesspinupdate.md) | The KsProcessPinUpdate function is called from within a filter-centric filter's AVStrMiniFilterProcess dispatch to update a process pin. |
| [KsPropertyHandler function](..\ks\nf-ks-kspropertyhandler.md) | Drivers call KsPropertyHandler function for IRP handling. |
| [KsPropertyHandlerWithAllocator function](..\ks\nf-ks-kspropertyhandlerwithallocator.md) | The KsPropertyHandlerWithAllocator performs the same handling as KsPropertyHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KsPublishDeviceProfile function](..\ks\nf-ks-kspublishdeviceprofile.md) | The KsPublishDeviceProfile API is called to publish device profile information. |
| [KsQueryDevicePnpObject function](..\ks\nf-ks-ksquerydevicepnpobject.md) | The KsQueryDevicePnpObject function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used. |
| [KsQueryInformationFile function](..\ks\nf-ks-ksqueryinformationfile.md) | The KsQueryInformationFile function performs an information query against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information request against the device object. |
| [KsQueryObjectAccessMask function](..\ks\nf-ks-ksqueryobjectaccessmask.md) | The KsQueryObjectAccessMask function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles. |
| [KsQueryObjectCreateItem function](..\ks\nf-ks-ksqueryobjectcreateitem.md) | The KsQueryObjectCreateItem function returns the create item assigned to the object when created. |
| [KsQuerySoftwareBusInterface function](..\swenum\nf-swenum-ksquerysoftwarebusinterface.md) | The KsQuerySoftwareBusInterface function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer. |
| [KsQueueWorkItem function](..\ks\nf-ks-ksqueueworkitem.md) | The KsQueueWorkItem function queues the specified work item with a worker previous created by the KsRegisterWorker function. |
| [KsReadFile function](..\ks\nf-ks-ksreadfile.md) | The KsReadFile function performs a read against the specified file object. |
| [KsRecalculateStackDepth function](..\ks\nf-ks-ksrecalculatestackdepth.md) | The KsRecalculateStackDepth function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the KsSetTargetDeviceObject function). If the PnP device object has been set on the underlying device header using KsSetDevicePnpAndBaseObject, that device is also taken into account when calculating the maximum stack depth. |
| [KsReferenceBusObject function](..\ks\nf-ks-ksreferencebusobject.md) | References the bus Physical device object. |
| [KsReferenceSoftwareBusObject function](..\swenum\nf-swenum-ksreferencesoftwarebusobject.md) | The KsReferenceSoftwareBusObject function increments the reference count of the demand-load bus enumerator object's PDO. |
| [KsRegisterAggregatedClientUnknown function](..\ks\nf-ks-ksregisteraggregatedclientunknown.md) | In a manner very similar to COM, the KsRegisterAggregatedClientUnknown function aggregates two objects |
| [KsRegisterCountedWorker function](..\ks\nf-ks-ksregistercountedworker.md) | Handles clients registering for use of a thread. |
| [KsRegisterFilterWithNoKSPins function](..\ks\nf-ks-ksregisterfilterwithnokspins.md) | The KsRegisterFilterWithNoKSPins function registers with DirectShow filters that have no kernel streaming pins and, therefore, do not stream in kernel mode. |
| [KsRegisterWorker function](..\ks\nf-ks-ksregisterworker.md) | The KsRegisterWorker function handles clients registering for use of a thread. |
| [KsReleaseCachedMdl function](..\ks\nf-ks-ksreleasecachedmdl.md) | The KsReleaseCachedMdl function is used to release the MDL acquired by the KsAcquireCachedMdl call. |
| [KsReleaseControl function](..\ks\nf-ks-ksreleasecontrol.md) | The KsReleaseControl function releases the control mutex for Object. |
| [KsReleaseDevice function](..\ks\nf-ks-ksreleasedevice.md) | The KsReleaseDevice function releases the device mutex and exits the critical region. |
| [KsReleaseDeviceSecurityLock function](..\ks\nf-ks-ksreleasedevicesecuritylock.md) | The KsReleaseDeviceSecurityLock function releases a previously acquired security lock on the device object header. |
| [KsReleaseIrpOnCancelableQueue function](..\ks\nf-ks-ksreleaseirponcancelablequeue.md) | The KsReleaseIrpOnCancelableQueue function releases an acquired IRP that is already on a queue that can be canceled. |
| [KsRemoveBusEnumInterface function](..\swenum\nf-swenum-ksremovebusenuminterface.md) | The KsRemoveBusEnumInterface function removes an interface to the demand-load bus enumerator object. |
| [KsRemoveIrpFromCancelableQueue function](..\ks\nf-ks-ksremoveirpfromcancelablequeue.md) | The KsRemoveIrpFromCancelableQueue function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status. |
| [KsRemoveItemFromObjectBag function](..\ks\nf-ks-ksremoveitemfromobjectbag.md) | The KsRemoveItemFromObjectBag function removes an item from an object bag. |
| [KsRemoveSpecificIrpFromCancelableQueue function](..\ks\nf-ks-ksremovespecificirpfromcancelablequeue.md) | The KsRemoveSpecificIrpFromCancelableQueue function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using KsRemoveIrpFromCancelableQueue, but that was not actually removed from the queue. |
| [KsResolveRequiredAttributes function](..\ksproxy\nf-ksproxy-ksresolverequiredattributes.md) | The KsResolveRequiredAttributes function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found. |
| [KsServiceBusEnumCreateRequest function](..\swenum\nf-swenum-ksservicebusenumcreaterequest.md) | The KsServiceBusEnumCreateRequest function services IRP_MJ_CREATE requests for the software bus device interface. |
| [KsServiceBusEnumPnpRequest function](..\swenum\nf-swenum-ksservicebusenumpnprequest.md) | The KsServiceBusEnumPnpRequest function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with KsCreateBusEnumObject. |
| [KsSetDefaultClockState function](..\ks\nf-ks-kssetdefaultclockstate.md) | The KsSetDefaultClockState function sets the current state of the clock that is used to reflect the current state of the underlying filter pin. |
| [KsSetDefaultClockTime function](..\ks\nf-ks-kssetdefaultclocktime.md) | The KsSetDefaultClockTime function sets the current time of the clock. |
| [KsSetDevicePnpAndBaseObject function](..\ks\nf-ks-kssetdevicepnpandbaseobject.md) | The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used. |
| [KsSetInformationFile function](..\ks\nf-ks-kssetinformationfile.md) | The KsSetInformationFile function performs an information set against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information set against the device object. |
| [KsSetMajorFunctionHandler function](..\ks\nf-ks-kssetmajorfunctionhandler.md) | The KsSetMajorFunctionHandler function sets the handler for a specified major function to use the internal dispatching. |
| [KsSetPowerDispatch function](..\ks\nf-ks-kssetpowerdispatch.md) | Sets the power dispatch function to be called when the driver object receives an IRP_MJ_POWER IRP. |
| [KsSetTargetDeviceObject function](..\ks\nf-ks-kssettargetdeviceobject.md) | The KsSetTargetDeviceObject function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices. |
| [KsSetTargetState function](..\ks\nf-ks-kssettargetstate.md) | Sets the enabled state of a target device associated with the specified object header. |
| [KsStreamIo function](..\ks\nf-ks-ksstreamio.md) | The KsStreamIo function performs a stream read or write against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates a read or write request against the device object. |
| [KsStreamPointerAdvance function](..\ks\nf-ks-ksstreampointeradvance.md) | The KsStreamPointerAdvance function advances a stream pointer to the next data frame. |
| [KsStreamPointerAdvanceOffsets function](..\ks\nf-ks-ksstreampointeradvanceoffsets.md) | The KsStreamPointerAdvanceOffsets function advances the offsets of StreamPointer. |
| [KsStreamPointerAdvanceOffsetsAndUnlock function](..\ks\nf-ks-ksstreampointeradvanceoffsetsandunlock.md) | The KsStreamPointerAdvanceOffsetsAndUnlock function advances StreamPointer the specified number of bytes into the stream (adjusting the OffsetIn and OffsetOut fields of StreamPointer as requested) and unlocks it. |
| [KsStreamPointerCancelTimeout function](..\ks\nf-ks-ksstreampointercanceltimeout.md) | The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer. |
| [KsStreamPointerClone function](..\ks\nf-ks-ksstreampointerclone.md) | The KsStreamPointerClone function creates a clone of a given stream pointer. |
| [KsStreamPointerDelete function](..\ks\nf-ks-ksstreampointerdelete.md) | The KsStreamPointerDelete function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred. |
| [KsStreamPointerGetIrp function](..\ks\nf-ks-ksstreampointergetirp.md) | The KsStreamPointerGetIrp function returns the IRP associated with the frame that is referenced by the given stream pointer. |
| [KsStreamPointerGetMdl function](..\ks\nf-ks-ksstreampointergetmdl.md) | The KsStreamPointerGetMdl function returns the MDL associated with the frame referenced by StreamPointer. |
| [KsStreamPointerGetNextClone function](..\ks\nf-ks-ksstreampointergetnextclone.md) | The KsStreamPointerGetNextClone function returns the clone stream pointer that was cloned immediately after the specified clone. |
| [KsStreamPointerLock function](..\ks\nf-ks-ksstreampointerlock.md) | The KsStreamPointerLock function attempts to lock the specified stream pointer. |
| [KsStreamPointerScheduleTimeout function](..\ks\nf-ks-ksstreampointerscheduletimeout.md) | The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer. |
| [KsStreamPointerSetStatusCode function](..\ks\nf-ks-ksstreampointersetstatuscode.md) | The KsStreamPointerSetStatusCode function allows specification of a successful or unsuccessful error code with which to complete the given IRP. |
| [KsStreamPointerUnlock function](..\ks\nf-ks-ksstreampointerunlock.md) | The KsStreamPointerUnlock function unlocks a stream pointer that has previously been locked by an acquisition function (KsGetXxxEdgeStreamPointer) or by KsStreamPointerLock. |
| [KsSynchronousDeviceControl function](..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md) | The KsSynchronousDeviceControl function issues a synchronous device I/O control operation to the KS object that is specified by a file handle. |
| [KsSynchronousIoControlDevice function](..\ks\nf-ks-kssynchronousiocontroldevice.md) | The KsSynchronousIoControlDevice function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL. |
| [KsTerminateDevice function](..\ks\nf-ks-ksterminatedevice.md) | The KsTerminateDevice function removes an AVStream device. |
| [KsTopologyPropertyHandler function](..\ks\nf-ks-kstopologypropertyhandler.md) | The KsTopologyPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Topology Property Set. The function uses the KSTOPOLOGY structure, which describes the set of information that is returned by this property set. |
| [KsUnregisterWorker function](..\ks\nf-ks-ksunregisterworker.md) | The KsUnregisterWorker function allows clients to unregister a worker. |
| [KsUnserializeObjectPropertiesFromRegistry function](..\ks\nf-ks-ksunserializeobjectpropertiesfromregistry.md) | The KsUnserializeObjectPropertiesFromRegistry function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data. |
| [KsValidateAllocatorCreateRequest function](..\ks\nf-ks-ksvalidateallocatorcreaterequest.md) | The KsValidateAllocatorCreateRequest function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success. |
| [KsValidateAllocatorFramingEx function](..\ks\nf-ks-ksvalidateallocatorframingex.md) | For system use only. |
| [KsValidateClockCreateRequest function](..\ks\nf-ks-ksvalidateclockcreaterequest.md) | The KsValidateClockCreateRequest function validates the clock creation request and returns the create structure associated with the request.This can only be called at PASSIVE_LEVEL. |
| [KsValidateConnectRequest function](..\ks\nf-ks-ksvalidateconnectrequest.md) | The KsValidateConnectRequest function validates a connection request and returns a pointer to the connection structure associated with the request.This function can only be called at PASSIVE_LEVEL. |
| [KsValidateTopologyNodeCreateRequest function](..\ks\nf-ks-ksvalidatetopologynodecreaterequest.md) | The KsValidateTopologyNodeCreateRequest function validates a topology node creation request and returns the create structure associated with the request. The function can only be called at PASSIVE_LEVEL. |
| [KsWriteFile function](..\ks\nf-ks-kswritefile.md) | The KsWriteFile function performs a write against the specified file object. |
| [StreamClassAbortOutstandingRequests function](..\strmini\nf-strmini-streamclassabortoutstandingrequests.md) | The StreamClassAbortOutstandingRequests routine aborts all outstanding requests, either to a particular stream, or to the entire driver. |
| [StreamClassCallAtNewPriority function](..\strmini\nf-strmini-streamclasscallatnewpriority.md) | The StreamClassCallAtNewPriority routine schedules a routine to be called at a different priority. |
| [StreamClassCompleteRequestAndMarkQueueReady function](..\strmini\nf-strmini-streamclasscompleterequestandmarkqueueready.md) | The StreamClassCompleteRequestAndMarkQueueReady routine completes a request, and signals the class driver that the minidriver is ready to receive a new request of the same type. |
| [StreamClassDebugAssert function](..\strmini\nf-strmini-streamclassdebugassert.md) | A minidriver can use the StreamClassDebugAssert routine in a checked build environment to fail an assert, causing the stream class driver to output a debug message and break into the kernel debugger. |
| [StreamClassDebugPrint function](..\strmini\nf-strmini-streamclassdebugprint.md) | In a checked build environment, the minidriver can use the StreamClassDebugPrint routine to print debug messages to the application window and to the Debugger Command window. |
| [StreamClassDeviceNotification function](..\strmini\nf-strmini-streamclassdevicenotification.md) | Minidrivers use the StreamClassDeviceNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred. |
| [StreamClassFilterReenumerateStreams function](..\strmini\nf-strmini-streamclassfilterreenumeratestreams.md) | Obsolete. Do not use. |
| [StreamClassGetDmaBuffer function](..\strmini\nf-strmini-streamclassgetdmabuffer.md) | The StreamClassGetDmaBuffer routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver. |
| [StreamClassGetNextEvent function](..\strmini\nf-strmini-streamclassgetnextevent.md) | Minidrivers can use the StreamClassGetNextEvent routine to search the event queue of a device or of a particular stream. |
| [StreamClassGetPhysicalAddress function](..\strmini\nf-strmini-streamclassgetphysicaladdress.md) | The StreamClassGetPhysicalAddress routine translates a virtual memory address to a physical memory address and locks the corresponding physical memory for a DMA operation. |
| [StreamClassQueryMasterClock function](..\strmini\nf-strmini-streamclassquerymasterclock.md) | When the minidriver calls the StreamClassQueryMasterClock routine, the class driver queries the appropriate time value of the master clock asynchronously, and passes the result to the routine passed in the ClockCallbackRoutine parameter. |
| [StreamClassQueryMasterClockSync function](..\strmini\nf-strmini-streamclassquerymasterclocksync.md) | The minidriver may call the StreamClassQueryMasterClockSync routine to synchronously query a stream's master clock. |
| [StreamClassReadWriteConfig function](..\strmini\nf-strmini-streamclassreadwriteconfig.md) | The StreamClassReadWriteConfig routine reads or writes configuration data for the minidriver's parent bus driver. |
| [StreamClassReenumerateStreams function](..\strmini\nf-strmini-streamclassreenumeratestreams.md) | Obsolete. Do not use. |
| [StreamClassRegisterAdapter function](..\strmini\nf-strmini-streamclassregisteradapter.md) | The StreamClassRegisterAdapter routine registers a stream class minidriver. |
| [StreamClassRegisterFilterWithNoKSPins function](..\strmini\nf-strmini-streamclassregisterfilterwithnokspins.md) | The StreamClassRegisterFilterWithNoKSPins routine is used to register filter drivers with Microsoft DirectShow that have no kernel streaming pins and, therefore, do not stream in kernel mode. |
| [StreamClassScheduleTimer function](..\strmini\nf-strmini-streamclassscheduletimer.md) | The minidriver calls the StreamClassScheduleTimer routine to schedule a timer, and to specify a routine that is called when the timer expires. |
| [StreamClassStreamNotification function](..\strmini\nf-strmini-streamclassstreamnotification.md) | Streams use the StreamClassStreamNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred. |
| [USBCAMD_AdapterReceivePacket function](..\usbcamdi\nf-usbcamdi-usbcamd_adapterreceivepacket.md) | The USBCAMD_AdapterReceivePacket function allows USBCAMD to process an adapter-based stream request block (SRB). |
| [USBCAMD_ControlVendorCommand function](..\usbcamdi\nf-usbcamdi-usbcamd_controlvendorcommand.md) | The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe. |
| [USBCAMD_Debug_LogEntry function](..\usbcamdi\nf-usbcamdi-usbcamd_debug_logentry.md) | The USBCAMD_Debug_LogEntry function is called by the camera minidriver to log debugging information to a file. |
| [USBCAMD_DriverEntry function](..\usbcamdi\nf-usbcamdi-usbcamd_driverentry.md) | The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together. |
| [USBCAMD_GetRegistryKeyValue function](..\usbcamdi\nf-usbcamdi-usbcamd_getregistrykeyvalue.md) | The USBCAMD_GetRegistryKeyValue function retrieves the device-instance-specific registry key value. |
| [USBCAMD_InitializeNewInterface function](..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md) | The USBCAMD_InitializeNewInterface function provides USBCAMD with all the necessary information to configure the camera minidriver to work correctly with the stream class driver and the USB bus driver. |
| [USBCAMD_SelectAlternateInterface function](..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md) | The USBCAMD_SelectAlternateInterface function selects an alternate setting within the USB video streaming interface. |
| [_KsEdit function](..\ks\nf-ks-_ksedit.md) | The _KsEdit function guarantees that a given item is dynamically allocated and associated with an AVStream object through the object bag. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PADAPTER_RECEIVE_PACKET_ROUTINE callback](..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md) | A camera minidriver's AdapterReceivePacket callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver. |
| [PCAM_ALLOCATE_BW_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine.md) | A camera minidriver's CamAllocateBandwidth callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_ALLOCATE_BW_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md) | A camera minidriver's CamAllocateBandwidthEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_CONFIGURE_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_configure_routine.md) | A camera minidriver's CamConfigure callback function configures the isochronous streaming interface. |
| [PCAM_CONFIGURE_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_configure_routine_ex.md) | A camera minidriver's CamConfigureEx callback function configures the isochronous streaming interface. |
| [PCAM_FREE_BW_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine.md) | A camera minidriver's CamFreeBandwidth callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth. |
| [PCAM_FREE_BW_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md) | A camera minidriver's CamFreeBandwidthEx callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth. |
| [PCAM_INITIALIZE_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_initialize_routine.md) | A camera minidriver's callback function initializes the device or performs any minidriver-specific clean-up that is required. |
| [PCAM_NEW_FRAME_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine.md) | A camera minidriver's CamNewVideoFrame callback function initializes a new video frame context structure. |
| [PCAM_NEW_FRAME_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine_ex.md) | A camera minidriver's CamNewVideoFrameEx callback function initializes a new video frame context structure. |
| [PCAM_PROCESS_PACKET_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine.md) | A camera minidriver's CamProcessUSBPacket callback function processes a USB packet. |
| [PCAM_PROCESS_PACKET_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine_ex.md) | A camera minidriver's CamProcessUSBPacketEx callback function processes a USB packet. |
| [PCAM_PROCESS_RAW_FRAME_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md) | A camera minidriver's CamProcessRawVideoFrame callback function decodes a raw video frame. |
| [PCAM_PROCESS_RAW_FRAME_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md) | A camera minidriver's CamProcessRawVideoFrameEx callback function decodes a raw video frame. |
| [PCAM_START_CAPTURE_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine.md) | A camera minidriver's CamStartCapture callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_START_CAPTURE_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md) | A camera minidriver's CamStartCaptureEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream. |
| [PCAM_STATE_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_state_routine.md) | A camera minidriver's state callback function restores a previously saved device context state or saves the current device context state. |
| [PCAM_STOP_CAPTURE_ROUTINE callback](..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine.md) | A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped. |
| [PCAM_STOP_CAPTURE_ROUTINE_EX callback](..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md) | A camera minidriver's CamStopCaptureEx callback function performs any processing after the stream is stopped. |
| [PCOMMAND_COMPLETE_FUNCTION callback](..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md) | A camera minidriver's CommandCompleteFunction callback function allows the camera minidriver to perform any additional tasks necessary to complete certain USBCAMD services |
| [PFNALLOCATOR_ALLOCATEFRAME callback](..\ks\nc-ks-pfnallocator_allocateframe.md) | The KStrAllocateFrame routine describes a vendor-supplied frame allocation function. |
| [PFNALLOCATOR_FREEFRAME callback](..\ks\nc-ks-pfnallocator_freeframe.md) | The KStrFreeFrame routine describes a vendor-supplied frame deallocation function. |
| [PFNAVCINTERSECTHANDLER callback](..\avc\nc-avc-pfnavcintersecthandler.md) | The AV/C intersect handler determines if the data ranges are compatible. |
| [PFNDEREFERENCEDEVICEOBJECT callback](..\ks\nc-ks-pfndereferencedeviceobject.md) | The driver can use this routine to decrement the reference count of the PDO. |
| [PFNKSADDEVENT callback](..\ks\nc-ks-pfnksaddevent.md) | An AVStream minidriver's AVStrMiniAddEvent routine is called when a client registers to be notified of an event. This routine is optional. |
| [PFNKSALLOCATOR callback](..\ks\nc-ks-pfnksallocator.md) | Minidrivers can optionally supply a callback function of type PFNKSALLOCATOR as a parameter in calls to KsEnableEventWithAllocator, KsPropertyHandlerWithAllocator, and KsMethodHandlerWithAllocator. |
| [PFNKSCANCELTIMER callback](..\ks\nc-ks-pfnkscanceltimer.md) | A streaming minidriver's KStrCancelTimer routine is called to cancel a custom timer object that was previously specified in the SetTimer parameter in a call to KsAllocateDefaultClockEx. |
| [PFNKSCLOCK_CORRELATEDTIME callback](..\ks\nc-ks-pfnksclock_correlatedtime.md) | KStrClockGetCorrelatedTime is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot. |
| [PFNKSCLOCK_GETTIME callback](..\ks\nc-ks-pfnksclock_gettime.md) | KStrClockGetTime is a system-supplied routine that retrieves the current system time. |
| [PFNKSCONTEXT_DISPATCH callback](..\ks\nc-ks-pfnkscontext_dispatch.md) | A streaming minidriver's KStrContextDispatch routine is called to process IRP_MJ_POWER IRPs. |
| [PFNKSCORRELATEDTIME callback](..\ks\nc-ks-pfnkscorrelatedtime.md) | A streaming minidriver's KStrCorrelatedTime routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time. |
| [PFNKSDEFAULTALLOCATE callback](..\ks\nc-ks-pfnksdefaultallocate.md) | An AVStream minidriver's AVStrMiniAllocate routine allocates a frame using the allocator specified in the Context parameter. |
| [PFNKSDEFAULTFREE callback](..\ks\nc-ks-pfnksdefaultfree.md) | An AVStream minidriver's AVStrMiniAllocatorFreeFrame routine frees the specified frame. |
| [PFNKSDELETEALLOCATOR callback](..\ks\nc-ks-pfnksdeleteallocator.md) | An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin. |
| [PFNKSDEVICE callback](..\ks\nc-ks-pfnksdevice.md) | An AVStream minidriver's AVStrMiniDevicePostStart routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start. |
| [PFNKSDEVICECREATE callback](..\ks\nc-ks-pfnksdevicecreate.md) | An AVStream minidriver's AVStrMiniDeviceAdd routine notifies the minidriver that AVStream's PnP AddDevice routine has completed. |
| [PFNKSDEVICEIRP callback](..\ks\nc-ks-pfnksdeviceirp.md) | An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.IRP_MN_QUERY_REMOVE_DEVICEIRP_MN_QUERY_STOP_DEVICEIRP_MN_QUERY_INTERFACE |
| [PFNKSDEVICEIRPVOID callback](..\ks\nc-ks-pfnksdeviceirpvoid.md) | An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.IRP_MN_CANCEL_STOP_DEVICEIRP_MN_CANCEL_REMOVE_DEVICEIRP_MN_REMOVE_DEVICEIRP_MN_STOP_DEVICEIRP_MN_SURPRISE_REMOVAL |
| [PFNKSDEVICEPNPSTART callback](..\ks\nc-ks-pfnksdevicepnpstart.md) | An AVStream minidriver's AVStrMiniDeviceStart routine is called when an IRP_MN_START_DEVICE request is sent for a specified device. |
| [PFNKSDEVICEQUERYCAPABILITIES callback](..\ks\nc-ks-pfnksdevicequerycapabilities.md) | An AVStream minidriver's AVStrMiniDeviceQueryCapabilities routine is called when an IRP_MN_QUERY_CAPABILITIES is dispatched by the device. |
| [PFNKSDEVICEQUERYPOWER callback](..\ks\nc-ks-pfnksdevicequerypower.md) | AVStream calls a minidriver's AVStrMiniDeviceQueryPower routine when it receives an IRP_MN_QUERY_POWER request. |
| [PFNKSDEVICESETPOWER callback](..\ks\nc-ks-pfnksdevicesetpower.md) | AVStream calls a minidriver's AVStrMiniDeviceSetPower routine when it receives an IRP_MN_SET_POWER. |
| [PFNKSFASTHANDLER callback](..\ks\nc-ks-pfnksfasthandler.md) | KStrFastHandler is a driver-supplied routine that handles a property or method request without the creation of an IRP. |
| [PFNKSFILTERIRP callback](..\ks\nc-ks-pfnksfilterirp.md) | An AVStream minidriver's AVStrMiniFilterCreate routine is called when a filter receives an IRP. |
| [PFNKSFILTERPROCESS callback](..\ks\nc-ks-pfnksfilterprocess.md) | An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing. |
| [PFNKSFILTERVOID callback](..\ks\nc-ks-pfnksfiltervoid.md) | An AVStream minidriver's AVStrMiniFilterReset routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at Acquire-time. |
| [PFNKSHANDLER callback](..\ks\nc-ks-pfnkshandler.md) | The minidriver-provided KStrMethodHandler routine is called when Kernel Streaming receives an IOCTL_KS_METHOD. Provide a pointer to this handler in the relevant KSMETHOD_ITEM structure. |
| [PFNKSINTERSECTHANDLER callback](..\ks\nc-ks-pfnksintersecthandler.md) | A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection. |
| [PFNKSINTERSECTHANDLEREX callback](..\ks\nc-ks-pfnksintersecthandlerex.md) | AVStream calls a minidriver's AVStrMiniIntersectHandlerEx routine to determine the highest quality intersection of two data ranges. |
| [PFNKSIRPLISTCALLBACK callback](..\ks\nc-ks-pfnksirplistcallback.md) | A streaming minidriver's KStrIrpListCallback routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated. |
| [PFNKSITEMFREECALLBACK callback](..\ks\nc-ks-pfnksitemfreecallback.md) | A streaming minidriver's KStrItemFreeCallback routine is called to free a previously allocated create item. KStrItemFreeCallback allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary. |
| [PFNKSPIN callback](..\ks\nc-ks-pfnkspin.md) | An AVStream minidriver's callback routine is called when |
| [PFNKSPINFRAMERETURN callback](..\ks\nc-ks-pfnkspinframereturn.md) | An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed. |
| [PFNKSPINHANDSHAKE callback](..\ks\nc-ks-pfnkspinhandshake.md) | An AVStream minidriver's AVStrMiniPinHandshake routine is called when AVStream receives a protocol handshake request that it does not handle. |
| [PFNKSPININITIALIZEALLOCATOR callback](..\ks\nc-ks-pfnkspininitializeallocator.md) | An AVStream minidriver's AVStrMiniInitializeAllocator routine initializes an allocator that will be associated with a pin. |
| [PFNKSPINIRP callback](..\ks\nc-ks-pfnkspinirp.md) | An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs |
| [PFNKSPINIRPCOMPLETION callback](..\ks\nc-ks-pfnkspinirpcompletion.md) | An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired. |
| [PFNKSPINPOWER callback](..\ks\nc-ks-pfnkspinpower.md) | An AVStream minidriver's AVStrMiniPinPower routine is called for pin-centric pins when the device is waking or entering a sleep state. |
| [PFNKSPINSETDATAFORMAT callback](..\ks\nc-ks-pfnkspinsetdataformat.md) | An AVStream minidriver's AVStrMiniPinSetDataFormat routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this KSPIN structure and a match for this KSDATARANGE structure. |
| [PFNKSPINSETDEVICESTATE callback](..\ks\nc-ks-pfnkspinsetdevicestate.md) | An AVStream minidriver's AVStrMiniPinSetDeviceState routine is called when the state of a KSPIN structure is changed due to the arrival of a connection state property 'set' IOCTL. |
| [PFNKSPINVOID callback](..\ks\nc-ks-pfnkspinvoid.md) | An AVStream minidriver's callback routine is called when |
| [PFNKSREMOVEEVENT callback](..\ks\nc-ks-pfnksremoveevent.md) | An AVStream minidriver's AVStrMiniRemoveEvent routine is called when a client requests to be removed from the notification queue for an event. This routine is optional. |
| [PFNKSSETTIMER callback](..\ks\nc-ks-pfnkssettimer.md) | A streaming minidriver's KStrSetTimer routine is called to generate DPC timer callbacks based on presentation time. |
| [PFNKSSTREAMPOINTER callback](..\ks\nc-ks-pfnksstreampointer.md) | AVStream calls a minidriver's AVStrMiniCancelCallback routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional. |
| [PFNQUERYREFERENCESTRING callback](..\ks\nc-ks-pfnqueryreferencestring.md) | This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool. |
| [PFNREFERENCEDEVICEOBJECT callback](..\ks\nc-ks-pfnreferencedeviceobject.md) | The driver can use this routine to increment the reference count of the PDO. |
| [PFNUSBCAMD_BulkReadWrite callback](..\usbcamdi\nc-usbcamdi-pfnusbcamd_bulkreadwrite.md) | The USBCAMD_BulkReadWrite service performs a read or write operation on the specified bulk pipe. |
| [PFNUSBCAMD_CancelBulkReadWrite callback](..\usbcamdi\nc-usbcamdi-pfnusbcamd_cancelbulkreadwrite.md) | The USBCAMD_CancelBulkReadWrite service cancels a pending bulk read or write request. |
| [PFNUSBCAMD_SetIsoPipeState callback](..\usbcamdi\nc-usbcamdi-pfnusbcamd_setisopipestate.md) | The USBCAMD_SetIsoPipeState service permits the camera minidriver to control the streaming state on the isochronous pipe. |
| [PFNUSBCAMD_SetVideoFormat callback](..\usbcamdi\nc-usbcamdi-pfnusbcamd_setvideoformat.md) | The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed. |
| [PFNUSBCAMD_WaitOnDeviceEvent callback](..\usbcamdi\nc-usbcamdi-pfnusbcamd_waitondeviceevent.md) | The USBCAMD_WaitOnDeviceEvent service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications. |
| [PHW_CANCEL_SRB callback](..\strmini\nc-strmini-phw_cancel_srb.md) | The class driver calls the minidriver's StrMiniCancelPacket routine to signal that a stream request has been canceled. |
| [PHW_EVENT_ROUTINE callback](..\strmini\nc-strmini-phw_event_routine.md) | The class driver calls the stream minidriver's StrMiniEvent routine to signal to a minidriver an event should be enabled or disabled. |
| [PHW_INTERRUPT callback](..\strmini\nc-strmini-phw_interrupt.md) | StrMiniInterrupt is the minidriver's interrupt service routine. |
| [PHW_PRIORITY_ROUTINE callback](..\strmini\nc-strmini-phw_priority_routine.md) | StrMiniPriorityRoutine is a minidriver-supplied callback routine to be executed at a specified priority level. |
| [PHW_QUERY_CLOCK_ROUTINE callback](..\strmini\nc-strmini-phw_query_clock_routine.md) | Each stream may have a clock associated to it. The class driver queries the clock by calling the stream minidriver-supplied StrMiniClock function, provided in each stream's HW_STREAM_OBJECT. |
| [PHW_RECEIVE_DEVICE_SRB callback](..\strmini\nc-strmini-phw_receive_device_srb.md) | The stream class driver calls the minidriver's StrMiniReceiveStreamControlPacket routine to handle I/O requests for a specific stream. |
| [PHW_REQUEST_TIMEOUT_HANDLER callback](..\strmini\nc-strmini-phw_request_timeout_handler.md) | The stream class driver calls the minidriver's StrMiniRequestTimeout routine to signal to the minidriver that a request has timed out. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [BUS_INTERFACE_MEDIUMS structure](..\ks\ns-ks-bus_interface_mediums.md) | . |
| [BUS_INTERFACE_REFERENCE structure](..\ks\ns-ks-bus_interface_reference.md) | A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use. |
| [KSALLOCATOR_FRAMING structure](..\ks\ns-ks-ksallocator_framing.md) | The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests. |
| [KSALLOCATOR_FRAMING_EX structure](..\ks\ns-ks-ksallocator_framing_ex.md) | The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter. |
| [KSATTRIBUTE structure](..\ks\ns-ks-ksattribute.md) | The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the KSDATAFORMAT and KSDATARANGE structures or the extended information based on the format and range specifiers. |
| [KSATTRIBUTE_LIST structure](..\ks\ns-ks-ksattribute_list.md) | The KSATTRIBUTE_LIST structure contains an attribute defined in a KSATTRIBUTE structure. |
| [KSAUTOMATION_TABLE_ structure](..\ks\ns-ks-ksautomation_table_.md) | The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events. |
| [KSBUFFER_ITEM structure](..\ks\ns-ks-ksbuffer_item.md) | The KSBUFFER_ITEM structure is used to store a list of data buffers copied from the event source, which can be retrieved by the event sink through KSEVENT_TYPE_QUERYBUFFER. |
| [KSCAMERA_PERFRAMESETTING_CAP_HEADER structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_cap_header.md) | This structure contains the header information for the per frame settings capabilities. |
| [KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_cap_item_header.md) | This structure contains the header information for a per-frame settings item. |
| [KSCAMERA_PERFRAMESETTING_CUSTOM_ITEM structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_custom_item.md) | This structure contains a custom item. |
| [KSCAMERA_PERFRAMESETTING_FRAME_HEADER structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_frame_header.md) | This structure contains the header information for a frame in a per-frame settings payload. |
| [KSCAMERA_PERFRAMESETTING_HEADER structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_header.md) | This structure contains header information for the per-frame settings payload. |
| [KSCAMERA_PERFRAMESETTING_ITEM_HEADER structure](..\ksmedia\ns-ksmedia-kscamera_perframesetting_item_header.md) | This structure contains the header information for a per-frame settings item. |
| [KSCLOCKINSTANCE structure](..\ksi\ns-ksi-ksclockinstance.md) | . |
| [KSCLOCK_CREATE structure](..\ks\ns-ks-ksclock_create.md) | The KSCLOCK_CREATE structure is used in clock create parameters for the KsCreateClock function. |
| [KSCLOCK_FUNCTIONTABLE structure](..\ks\ns-ks-ksclock_functiontable.md) | The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock. |
| [KSCOMPONENTID structure](..\ks\ns-ks-kscomponentid.md) | The KSCOMPONENTID structure contains unique identifiers that describe an individual kernel streaming object. |
| [KSCORRELATED_TIME structure](..\ks\ns-ks-kscorrelated_time.md) | The KSCORRELATED_TIME structure contains a clock time as well as the corresponding number of clock ticks since system boot. |
| [KSDATAFORMAT structure](..\ks\ns-ks-ksdataformat.md) | The KSDATAFORMAT structure is a variable-length structure that describes a data format. |
| [KSDISPATCH_TABLE structure](..\ks\ns-ks-ksdispatch_table.md) | The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines. |
| [KSDPC_ITEM structure](..\ks\ns-ks-ksdpc_item.md) | The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL. |
| [KSERROR structure](..\ks\ns-ks-kserror.md) | The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers. |
| [KSEVENTDATA structure](..\ks\ns-ks-kseventdata.md) | Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method. |
| [KSEVENT_ITEM structure](..\ks\ns-ks-ksevent_item.md) | The KSEVENT_ITEM structure describe a minidriver's support for a specific event within an event set. |
| [KSEVENT_SET structure](..\ks\ns-ks-ksevent_set.md) | The KSEVENT_SET structure describes the events that comprise a kernel streaming event set. |
| [KSEVENT_TIME_INTERVAL structure](..\ks\ns-ks-ksevent_time_interval.md) | The KSEVENT_TIME_INTERVAL structure is used in various events within the KSEVENTSETID_Clock event set. |
| [KSEVENT_TIME_MARK structure](..\ks\ns-ks-ksevent_time_mark.md) | The KSEVENT_TIME_MARK structure is used in various events within the KSEVENTSETID_Clock event set. |
| [KSEVENT_TUNER_INITIATE_SCAN_S structure](..\ksmedia\ns-ksmedia-ksevent_tuner_initiate_scan_s.md) | The KSEVENT_TUNER_INITIATE_SCAN_S structure is used in the KSEVENT_TUNER_INITIATE_SCAN event within the EVENTSETID_TUNER event set. |
| [KSE_NODE structure](..\ks\ns-ks-kse_node.md) | The KSE_NODE structure specifies an event request on a specific node. |
| [KSE_PIN structure](..\ks\ns-ks-kse_pin.md) | . |
| [KSFASTMETHOD_ITEM structure](..\ks\ns-ks-ksfastmethod_item.md) | Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching. |
| [KSFASTPROPERTY_ITEM structure](..\ks\ns-ks-ksfastproperty_item.md) | The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching. |
| [KSFRAMETIME structure](..\ks\ns-ks-ksframetime.md) | The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next &#0034;frame&#0034; of data, and flags associated with that frame. |
| [KSGRAPHMANAGER_FUNCTIONTABLE structure](..\ks\ns-ks-ksgraphmanager_functiontable.md) | . |
| [KSHANDSHAKE structure](..\ks\ns-ks-kshandshake.md) | The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface. |
| [KSIDEFAULTCLOCK structure](..\ksi\ns-ksi-ksidefaultclock.md) | . |
| [KSIDENTIFIER structure](..\ks\ns-ks-ksidentifier.md) | The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set. |
| [KSINTERVAL structure](..\ks\ns-ks-ksinterval.md) | The KSINTERVAL structure specifies a base time and time interval for recurring events. |
| [KSMETHOD_ITEM structure](..\ks\ns-ks-ksmethod_item.md) | The KSMETHOD_ITEM structure describes a single method within a method set. |
| [KSMETHOD_SET structure](..\ks\ns-ks-ksmethod_set.md) | The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set. |
| [KSMULTIPLE_ITEM structure](..\ks\ns-ks-ksmultiple_item.md) | The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries. |
| [KSM_NODE structure](..\ks\ns-ks-ksm_node.md) | Just as KSP_NODE is used for properties on a node, the KSM_NODE structure is used for methods on a node. |
| [KSNODE_CREATE structure](..\ks\ns-ks-ksnode_create.md) | The KSNODE_CREATE structure describes the set of information used to create the node handle. |
| [KSOBJECT_CREATE structure](..\ks\ns-ks-ksobject_create.md) | The KSOBJECT_CREATE structure contains an array of create handlers for base object classes supported by this device object. |
| [KSOBJECT_CREATE_ITEM structure](..\ks\ns-ks-ksobject_create_item.md) | The KSOBJECT_CREATE_ITEM structure is used to look up the string passed to a create request. |
| [KSPIN_CINSTANCES structure](..\ks\ns-ks-kspin_cinstances.md) | . |
| [KSPIN_CONNECT structure](..\ks\ns-ks-kspin_connect.md) | Clients use the KSPIN_CONNECT structure to describe the connection they request from a driver in a KsCreatePin call. |
| [KSPIN_DESCRIPTOR structure](..\ks\ns-ks-kspin_descriptor.md) | The KSPIN_DESCRIPTOR structure describes the basic KSPROPSETID_Pin properties of a pin type. |
| [KSPIN_MDL_CACHING_NOTIFICATION structure](..\ks\ns-ks-kspin_mdl_caching_notification.md) | This structure is used internally by the operating system. |
| [KSPIN_MDL_CACHING_NOTIFICATION32 structure](..\ks\ns-ks-kspin_mdl_caching_notification32.md) | This structure is used internally by the operating system. |
| [KSPIN_PHYSICALCONNECTION structure](..\ks\ns-ks-kspin_physicalconnection.md) | A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a KSPROPERTY_PIN_PHYSICALCONNECTION request. |
| [KSPRIORITY structure](..\ks\ns-ks-kspriority.md) | The KSPRIORITY structure is used to specify priority and is used with the KSPROPERTY_CONNECTION_PRIORITY property. |
| [KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_allocator_control_capture_caps_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported. |
| [KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure](..\ksmedia\ns-ksmedia-ksproperty_allocator_control_capture_interleave_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible. |
| [KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure](..\ksmedia\ns-ksmedia-ksproperty_allocator_control_surface_size_s.md) | The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface. |
| [KSPROPERTY_BOUNDS_LONG structure](..\ks\ns-ks-ksproperty_bounds_long.md) | The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property. |
| [KSPROPERTY_BOUNDS_LONGLONG structure](..\ks\ns-ks-ksproperty_bounds_longlong.md) | The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property. |
| [KSPROPERTY_CAMERACONTROL_FLASH_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_flash_s.md) | Describes flash control properties in the PROPSETID_VIDCAP_CAMERACONTROL_FLASH camera control property set. This structure specifies property values that are used by applications to configure the camera's flash. |
| [KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_focal_length_s.md) | The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property. |
| [KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_image_pin_capability_s.md) | Describes image pin control properties in the PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY camera control property set. |
| [KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_node_focal_length_s.md) | The KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S structure returns node-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property. |
| [KSPROPERTY_CAMERACONTROL_NODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_node_s.md) | The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. This structure specifies property values in requests to the USB Video Class driver. |
| [KSPROPERTY_CAMERACONTROL_NODE_S2 structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_node_s2.md) | The KSPROPERTY_CAMERACONTROL_NODE_S2 structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time. This structure specifies property values in requests to the USB video class driver. |
| [KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_region_of_interest_s.md) | Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set. |
| [KSPROPERTY_CAMERACONTROL_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s.md) | The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. |
| [KSPROPERTY_CAMERACONTROL_S2 structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s2.md) | The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time. |
| [KSPROPERTY_CAMERACONTROL_S_EX structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s_ex.md) | Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. |
| [KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_videostabilization_mode_s.md) | Describes video stabilization control properties in the PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION camera control property set. This structure specifies property values that are used in requests to the camera driver. |
| [KSPROPERTY_CROSSBAR_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_crossbar_caps_s.md) | The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device. |
| [KSPROPERTY_CROSSBAR_PININFO_S structure](..\ksmedia\ns-ksmedia-ksproperty_crossbar_pininfo_s.md) | The KSPROPERTY_CROSSBAR_PININFO_S structure describes the crossbar pin information for a device. |
| [KSPROPERTY_CROSSBAR_ROUTE_S structure](..\ksmedia\ns-ksmedia-ksproperty_crossbar_route_s.md) | The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin. |
| [KSPROPERTY_DESCRIPTION structure](..\ks\ns-ks-ksproperty_description.md) | The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property. |
| [KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure](..\ksmedia\ns-ksmedia-ksproperty_droppedframes_current_s.md) | The KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure describes the dropped frame information from the minidriver. |
| [KSPROPERTY_EXTDEVICE_S structure](..\ksmedia\ns-ksmedia-ksproperty_extdevice_s.md) | The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities. |
| [KSPROPERTY_EXTXPORT_NODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_extxport_node_s.md) | The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities. |
| [KSPROPERTY_EXTXPORT_S structure](..\ksmedia\ns-ksmedia-ksproperty_extxport_s.md) | The KSPROPERTY_EXTXPORT_S structure describes an external transport and its capabilities. |
| [KSPROPERTY_ITEM structure](..\ks\ns-ks-ksproperty_item.md) | Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set. |
| [KSPROPERTY_MEDIAAVAILABLE structure](..\ks\ns-ks-ksproperty_mediaavailable.md) | The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter. |
| [KSPROPERTY_MEMBERSHEADER structure](..\ks\ns-ks-ksproperty_membersheader.md) | A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges. |
| [KSPROPERTY_MEMBERSLIST structure](..\ks\ns-ks-ksproperty_memberslist.md) | The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property. |
| [KSPROPERTY_POSITIONS structure](..\ks\ns-ks-ksproperty_positions.md) | The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream. |
| [KSPROPERTY_SELECTOR_NODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_selector_node_s.md) | The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_SELECTOR property set. |
| [KSPROPERTY_SELECTOR_S structure](..\ksmedia\ns-ksmedia-ksproperty_selector_s.md) | The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the PROPSETID_VIDCAP_SELECTOR property set. |
| [KSPROPERTY_SERIAL structure](..\ks\ns-ks-ksproperty_serial.md) | The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure. |
| [KSPROPERTY_SERIALHDR structure](..\ks\ns-ks-ksproperty_serialhdr.md) | The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties. |
| [KSPROPERTY_SET structure](..\ks\ns-ks-ksproperty_set.md) | A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set. |
| [KSPROPERTY_STEPPING_LONG structure](..\ks\ns-ks-ksproperty_stepping_long.md) | The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property. |
| [KSPROPERTY_STEPPING_LONGLONG structure](..\ks\ns-ks-ksproperty_stepping_longlong.md) | The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property. |
| [KSPROPERTY_TIMECODE_NODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_timecode_node_s.md) | The KSPROPERTY_TIMECODE_NODE_S structure describes a timecode. |
| [KSPROPERTY_TIMECODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_timecode_s.md) | The KSPROPERTY_TIMECODE_S structure describes a timecode. |
| [KSPROPERTY_TUNER_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_caps_s.md) | The KSPROPERTY_TUNER_CAPS_S structure describes the hardware capabilities of TV and radio tuning devices. |
| [KSPROPERTY_TUNER_FREQUENCY_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_frequency_s.md) | The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device. |
| [KSPROPERTY_TUNER_IF_MEDIUM_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_if_medium_s.md) | The KSPROPERTY_TUNER_IF_MEDIUM_S structure returns the Medium GUID for the pin that is capable of supporting tuning to an intermediate frequency. |
| [KSPROPERTY_TUNER_INPUT_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_input_s.md) | The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs. |
| [KSPROPERTY_TUNER_MODE_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_mode_caps_s.md) | The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices. |
| [KSPROPERTY_TUNER_MODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_mode_s.md) | The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device. |
| [KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_networktype_scan_caps_s.md) | The KSPROPERTY_TUNER_NETWORKTYPE_SCAN_CAPS_S structure describes the scanning capabilities of a broadcast network type that a tuning device supports. |
| [KSPROPERTY_TUNER_SCAN_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_scan_caps_s.md) | The KSPROPERTY_TUNER_SCAN_CAPS_S structure describes the hardware scanning capabilities of a tuning device. |
| [KSPROPERTY_TUNER_SCAN_STATUS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_scan_status_s.md) | The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation. |
| [KSPROPERTY_TUNER_STANDARD_MODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_standard_mode_s.md) | The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself. |
| [KSPROPERTY_TUNER_STANDARD_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_standard_s.md) | The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM. |
| [KSPROPERTY_TUNER_STATUS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tuner_status_s.md) | The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency. |
| [KSPROPERTY_TVAUDIO_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_tvaudio_caps_s.md) | The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities. |
| [KSPROPERTY_TVAUDIO_S structure](..\ksmedia\ns-ksmedia-ksproperty_tvaudio_s.md) | The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings. |
| [KSPROPERTY_VALUES structure](..\ks\ns-ks-ksproperty_values.md) | The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property. |
| [KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocompression_getinfo_s.md) | The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device. |
| [KSPROPERTY_VIDEOCOMPRESSION_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocompression_s.md) | The KSPROPERTY_VIDEOCOMPRESSION_S structure describes a single KSPROPERTY_VIDEOCOMPRESSION_Xxx property of a specified stream. |
| [KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocontrol_actual_frame_rate_s.md) | The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests. |
| [KSPROPERTY_VIDEOCONTROL_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocontrol_caps_s.md) | The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities. |
| [KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocontrol_frame_rates_s.md) | The KSPROPERTY_VIDEOCONTROL_FRAME_RATES structure describes available frame rates in 100-nanosecond units. |
| [KSPROPERTY_VIDEOCONTROL_MODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_videocontrol_mode_s.md) | The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities. |
| [KSPROPERTY_VIDEODECODER_CAPS_S structure](..\ksmedia\ns-ksmedia-ksproperty_videodecoder_caps_s.md) | The KSPROPERTY_VIDEODECODER_CAPS_S structure describes the hardware capabilities of the video decoder device. |
| [KSPROPERTY_VIDEODECODER_S structure](..\ksmedia\ns-ksmedia-ksproperty_videodecoder_s.md) | The KSPROPERTY_VIDEODECODER_S structure describes property settings in the PROPSETID_VIDCAP_VIDEODECODER property set. |
| [KSPROPERTY_VIDEODECODER_STATUS_S structure](..\ksmedia\ns-ksmedia-ksproperty_videodecoder_status_s.md) | The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in. |
| [KSPROPERTY_VIDEOPROCAMP_NODE_S structure](..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_node_s.md) | The KSPROPERTY_VIDEOPROCAMP_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set. |
| [KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure](..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_node_s2.md) | The KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set that use two values at the same time. |
| [KSPROPERTY_VIDEOPROCAMP_S structure](..\ksmedia\ns-ksmedia-ksproperty_videoprocamp_s.md) | The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set. |
| [KSP_NODE structure](..\ks\ns-ks-ksp_node.md) | Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request. |
| [KSP_NODE_ESPID structure](..\bdamedia\ns-bdamedia-ksp_node_espid.md) | The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes. |
| [KSP_PIN structure](..\ks\ns-ks-ksp_pin.md) | Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request. |
| [KSP_TIMEFORMAT structure](..\ks\ns-ks-ksp_timeformat.md) | The KSP_TIMEFORMAT structure corresponds to KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT. |
| [KSQUALITY structure](..\ks\ns-ks-ksquality.md) | The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers. |
| [KSQUALITY_MANAGER structure](..\ks\ns-ks-ksquality_manager.md) | The KSQUALITY_MANAGER structure is used with the KSPROPERTY_STREAM_QUALITY property and contains the handle of the quality manager sink and a context to pass in the quality complaints. |
| [KSQUERYBUFFER structure](..\ks\ns-ks-ksquerybuffer.md) | The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER. |
| [KSRATE structure](..\ks\ns-ks-ksrate.md) | The query is passed a KSRATE structure appended to the property containing the rate request (known as a KSRATE_CAPABILITY structure), and is returned a KSRATE structure filled in with the capability given the rate request. |
| [KSRATE_CAPABILITY structure](..\ks\ns-ks-ksrate_capability.md) | The client uses the KSRATE_CAPABILITY structure in a KSPROPERTY_STREAM_RATECAPABILITY property request. |
| [KSRELATIVEEVENT structure](..\ks\ns-ks-ksrelativeevent.md) | The KSPROPERTY_CONNECTION_STARTAT property is passed a KSRELATIVEEVENT structure. |
| [KSRESOLUTION structure](..\ks\ns-ks-ksresolution.md) | The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock. |
| [KSSCATTER_GATHER structure](..\strmini\ns-strmini-ksscatter_gather.md) | . |
| [KSSTREAMALLOCATOR_FUNCTIONTABLE structure](..\ks\ns-ks-ksstreamallocator_functiontable.md) | Clients can request the function table of a given allocator by sending a KSSTREAMALLOCATOR_FUNCTIONTABLE structure in a KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE property request. |
| [KSSTREAMALLOCATOR_STATUS structure](..\ks\ns-ks-ksstreamallocator_status.md) | The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator. |
| [KSSTREAMALLOCATOR_STATUS_EX structure](..\ks\ns-ks-ksstreamallocator_status_ex.md) | Client use KSSTREAMALLOCATOR_STATUS_EX to query the status for allocators supporting the extended allocator framing. |
| [KSSTREAM_HEADER structure](..\ks\ns-ks-ksstream_header.md) | The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin. |
| [KSSTREAM_METADATA_INFO structure](..\ks\ns-ks-ksstream_metadata_info.md) | This structure contains the metadata information that is passed down to the driver. |
| [KSSTREAM_UVC_METADATA structure](..\ks\ns-ks-ksstream_uvc_metadata.md) | The KSSTREAM_UVC_METADATA structure contains start and end of frame timestamp information. |
| [KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure](..\ks\ns-ks-ksstream_uvc_metadatatype_timestamp.md) | The KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure contains USB video class (UVC) clock and timestamp information. |
| [KSTIME structure](..\ks\ns-ks-kstime.md) | The KSTIME structure specifies a time stamp that can be used to indicate stream position. |
| [KSTOPOLOGY structure](..\ks\ns-ks-kstopology.md) | The KSTOPOLOGY structure describes the topology of pins and nodes. |
| [KSTOPOLOGY_CONNECTION structure](..\ks\ns-ks-kstopology_connection.md) | The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter. |
| [KSVPMAXPIXELRATE structure](..\ksmedia\ns-ksmedia-ksvpmaxpixelrate.md) | The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port. |
| [KSVPSURFACEPARAMS structure](..\ksmedia\ns-ksmedia-ksvpsurfaceparams.md) | The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface. |
| [KSWAVE_BUFFER structure](..\ksmedia\ns-ksmedia-kswave_buffer.md) | The KSWAVE_BUFFER structure is used to describe a sample buffer. |
| [KSWAVE_COMPATCAPS structure](..\ksmedia\ns-ksmedia-kswave_compatcaps.md) | The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device. |
| [KSWAVE_INPUT_CAPABILITIES structure](..\ksmedia\ns-ksmedia-kswave_input_capabilities.md) | The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device. |
| [KSWAVE_OUTPUT_CAPABILITIES structure](..\ksmedia\ns-ksmedia-kswave_output_capabilities.md) | The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device. |
| [KSWAVE_VOLUME structure](..\ksmedia\ns-ksmedia-kswave_volume.md) | The KSWAVE_VOLUME structure is used to describe sample volume. |
| [KS_AM_ExactRateChange structure](..\ksmedia\ns-ksmedia-ks_am_exactratechange.md) | The KS_AM_ExactRateChange structure is not yet implemented. |
| [KS_AM_SimpleRateChange structure](..\ksmedia\ns-ksmedia-ks_am_simpleratechange.md) | The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream. |
| [KS_COMPRESSION structure](..\ks\ns-ks-ks_compression.md) | The KS_COMPRESSION structure defines the compression of frames on an output pin. |
| [KS_FRAMING_ITEM structure](..\ks\ns-ks-ks_framing_item.md) | The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin. |
| [KS_FRAMING_RANGE structure](..\ks\ns-ks-ks_framing_range.md) | The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item. |
| [KS_FRAMING_RANGE_WEIGHTED structure](..\ks\ns-ks-ks_framing_range_weighted.md) | Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes. |
| [LAMP_CAPABILITIES_COLOR structure](..\lamp\ns-lamp-lamp_capabilities_color.md) | This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR. |
| [LAMP_CAPABILITIES_WHITE structure](..\lamp\ns-lamp-lamp_capabilities_white.md) | This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE. |
| [LAMP_INTENSITY_COLOR structure](..\lamp\ns-lamp-lamp_intensity_color.md) | This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_COLOR and IOCTL_LAMP_SET_INTENSITY_COLOR. |
| [LAMP_INTENSITY_WHITE structure](..\lamp\ns-lamp-lamp_intensity_white.md) | This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_WHITE and IOCTL_LAMP_SET_INTENSITY_WHITE. |
| [MEDIUM_INFO structure](..\ksmedia\ns-ksmedia-medium_info.md) | The MEDIUM_INFO structure describes the media loaded into an external device. |
| [OPTIMAL_WEIGHT_TOTALS structure](..\ksproxy\ns-ksproxy-optimal_weight_totals.md) | . |
| [PID_MAP structure](..\bdatypes\ns-bdatypes-pid_map.md) | The PID_MAP structure describes a group of packets in the output stream of a packet identifier (PID) filter. This group consists of packets that are identified with an identical PID and contain particular media content. |
| [TRANSPORT_STATE structure](..\ksmedia\ns-ksmedia-transport_state.md) | The TRANSPORT_STATE structure |
| [TUNER_ANALOG_CAPS_S structure](..\ksmedia\ns-ksmedia-tuner_analog_caps_s.md) | The TUNER_ANALOG_CAPS_S structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network. |
| [USBCAMD_INTERFACE structure](..\usbcamdi\ns-usbcamdi-usbcamd_interface.md) | The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces. |
| [VRAM_SURFACE_INFO structure](..\ksmedia\ns-ksmedia-vram_surface_info.md) | The VRAM_SURFACE_INFO structure describes a region of system or display memory into which an AVStream minidriver captures audio or video data. |
| [VRAM_SURFACE_INFO_PROPERTY_S structure](..\ksmedia\ns-ksmedia-vram_surface_info_property_s.md) | The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set. |
| [_ALLOCATOR_PROPERTIES_EX structure](..\ksproxy\ns-ksproxy-_allocator_properties_ex.md) | The ALLOCATOR_PROPERTIES_EX structure is for proxy use and not recommended for application use. ALLOCATOR_PROPERTIES_EX contains information that describes properties of an allocator. |
| [_AVCCONNECTINFO structure](..\avc\ns-avc-_avcconnectinfo.md) | The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVCPRECONNECTINFO structure](..\avc\ns-avc-_avcpreconnectinfo.md) | The AVCPRECONNECTINFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVCSTRM_BUFFER_STRUCT structure](..\avcstrm\ns-avcstrm-_avcstrm_buffer_struct.md) | The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to avcstrm.sys for read or write operations. |
| [_AVCSTRM_FORMAT_INFO structure](..\avcstrm\ns-avcstrm-_avcstrm_format_info.md) | The AVCSTRM_FORMAT_INFO structure is used to describe a data stream. |
| [_AVCSTRM_OPEN_STRUCT structure](..\avcstrm\ns-avcstrm-_avcstrm_open_struct.md) | The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened. |
| [_AVC_COMMAND_IRB structure](..\avc\ns-avc-_avc_command_irb.md) | The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair. |
| [_AVC_EXT_PLUG_COUNTS structure](..\avc\ns-avc-_avc_ext_plug_counts.md) | The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit. |
| [_AVC_IRB structure](..\avc\ns-avc-_avc_irb.md) | The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored. |
| [_AVC_MULTIFUNC_IRB structure](..\avc\ns-avc-_avc_multifunc_irb.md) | The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union. |
| [_AVC_PEER_DO_LIST structure](..\avc\ns-avc-_avc_peer_do_list.md) | The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of avc.sys. |
| [_AVC_PEER_DO_LOCATOR structure](..\avc\ns-avc-_avc_peer_do_locator.md) | The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of avc.sys. |
| [_AVC_PIN_COUNT structure](..\avc\ns-avc-_avc_pin_count.md) | The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device. |
| [_AVC_PIN_DESCRIPTOR structure](..\avc\ns-avc-_avc_pin_descriptor.md) | The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device. |
| [_AVC_PIN_ID structure](..\avc\ns-avc-_avc_pin_id.md) | The AVC_PIN_ID structure describes a pin on a subunit. |
| [_AVC_PRECONNECT_INFO structure](..\avc\ns-avc-_avc_preconnect_info.md) | The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device. |
| [_AVC_SETCONNECT_INFO structure](..\avc\ns-avc-_avc_setconnect_info.md) | The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVC_STREAM_REQUEST_BLOCK structure](..\avcstrm\ns-avcstrm-_avc_stream_request_block.md) | The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by avcstrm.sys. |
| [_AVC_SUBUNIT_ADDR_SPEC structure](..\avc\ns-avc-_avc_subunit_addr_spec.md) | The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of avc.sys to describe virtual subunit addresses. |
| [_AVC_SUBUNIT_INFO_BLOCK structure](..\avc\ns-avc-_avc_subunit_info_block.md) | The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information. |
| [_AVC_UNIQUE_ID structure](..\avc\ns-avc-_avc_unique_id.md) | The AVC_UNIQUE_ID describe the unique ID of the AV/C unit. |
| [_BDANODE_DESCRIPTOR structure](..\bdatypes\ns-bdatypes-_bdanode_descriptor.md) | The BDANODE_DESCRIPTOR structure describes a BDA node. |
| [_BDA_BUFFER structure](..\bdatypes\ns-bdatypes-_bda_buffer.md) | . |
| [_BDA_CAS_CHECK_ENTITLEMENTTOKEN structure](..\bdatypes\ns-bdatypes-_bda_cas_check_entitlementtoken.md) | . |
| [_BDA_CAS_CLOSEMMIDATA structure](..\bdatypes\ns-bdatypes-_bda_cas_closemmidata.md) | . |
| [_BDA_CAS_CLOSE_MMIDIALOG structure](..\bdatypes\ns-bdatypes-_bda_cas_close_mmidialog.md) | . |
| [_BDA_CAS_OPENMMIDATA structure](..\bdatypes\ns-bdatypes-_bda_cas_openmmidata.md) | . |
| [_BDA_CAS_REQUESTTUNERDATA structure](..\bdatypes\ns-bdatypes-_bda_cas_requesttunerdata.md) | . |
| [_BDA_CA_MODULE_UI structure](..\bdatypes\ns-bdatypes-_bda_ca_module_ui.md) | The BDA_CA_MODULE_UI structure describes the user interface (UI) that conditional access (CA) plugins can display. |
| [_BDA_DISEQC_RESPONSE structure](..\bdatypes\ns-bdatypes-_bda_diseqc_response.md) | . |
| [_BDA_DISEQC_SEND structure](..\bdatypes\ns-bdatypes-_bda_diseqc_send.md) | . |
| [_BDA_DRM_DRMSTATUS structure](..\bdatypes\ns-bdatypes-_bda_drm_drmstatus.md) | . |
| [_BDA_DVBT2_L1_SIGNALLING_DATA structure](..\bdatypes\ns-bdatypes-_bda_dvbt2_l1_signalling_data.md) | . |
| [_BDA_ETHERNET_ADDRESS structure](..\bdatypes\ns-bdatypes-_bda_ethernet_address.md) | . |
| [_BDA_ETHERNET_ADDRESS_LIST structure](..\bdatypes\ns-bdatypes-_bda_ethernet_address_list.md) | . |
| [_BDA_FILTER_TEMPLATE structure](..\bdasup\ns-bdasup-_bda_filter_template.md) | The BDA_FILTER_TEMPLATE structure describes the template topology for a BDA filter. |
| [_BDA_GDDS_DATA structure](..\bdatypes\ns-bdatypes-_bda_gdds_data.md) | . |
| [_BDA_GDDS_DATATYPE structure](..\bdatypes\ns-bdatypes-_bda_gdds_datatype.md) | . |
| [_BDA_IPv4_ADDRESS structure](..\bdatypes\ns-bdatypes-_bda_ipv4_address.md) | . |
| [_BDA_IPv4_ADDRESS_LIST structure](..\bdatypes\ns-bdatypes-_bda_ipv4_address_list.md) | . |
| [_BDA_IPv6_ADDRESS structure](..\bdatypes\ns-bdatypes-_bda_ipv6_address.md) | . |
| [_BDA_IPv6_ADDRESS_LIST structure](..\bdatypes\ns-bdatypes-_bda_ipv6_address_list.md) | . |
| [_BDA_ISDBCAS_REQUESTHEADER structure](..\bdatypes\ns-bdatypes-_bda_isdbcas_requestheader.md) | . |
| [_BDA_ISDBCAS_RESPONSEDATA structure](..\bdatypes\ns-bdatypes-_bda_isdbcas_responsedata.md) | . |
| [_BDA_PID_MAP structure](..\bdatypes\ns-bdatypes-_bda_pid_map.md) | The BDA_PID_MAP structure describes a type of data to filter out of the input stream of a packet identifier (PID) filter and then pass to a downstream filter. |
| [_BDA_PID_UNMAP structure](..\bdatypes\ns-bdatypes-_bda_pid_unmap.md) | The BDA_PID_UNMAP structure describes packet types to stop filtering from the input stream of a packet identifier (PID) filter. These packet types are identified with PIDs. |
| [_BDA_PIN_PAIRING structure](..\bdasup\ns-bdasup-_bda_pin_pairing.md) | The BDA_PIN_PAIRING structure describes the topology between a pair of input and output pins. |
| [_BDA_PROGRAM_PID_LIST structure](..\bdatypes\ns-bdatypes-_bda_program_pid_list.md) | The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID). |
| [_BDA_RATING_PINRESET structure](..\bdatypes\ns-bdatypes-_bda_rating_pinreset.md) | . |
| [_BDA_SCAN_CAPABILTIES structure](..\bdatypes\ns-bdatypes-_bda_scan_capabilties.md) | . |
| [_BDA_SCAN_START structure](..\bdatypes\ns-bdatypes-_bda_scan_start.md) | . |
| [_BDA_SCAN_STATE structure](..\bdatypes\ns-bdatypes-_bda_scan_state.md) | . |
| [_BDA_SIGNAL_TIMEOUTS structure](..\bdatypes\ns-bdatypes-_bda_signal_timeouts.md) | . |
| [_BDA_STRING structure](..\bdatypes\ns-bdatypes-_bda_string.md) | . |
| [_BDA_TABLE_SECTION structure](..\bdatypes\ns-bdatypes-_bda_table_section.md) | The BDA_TABLE_SECTION structure describes a table section. |
| [_BDA_TEMPLATE_CONNECTION structure](..\bdatypes\ns-bdatypes-_bda_template_connection.md) | The BDA_TEMPLATE_CONNECTION structure describes the template for a BDA connection in terms of where it begins and ends. |
| [_BDA_TEMPLATE_PIN_JOINT structure](..\bdatypes\ns-bdatypes-_bda_template_pin_joint.md) | The BDA_TEMPLATE_PIN_JOINT structure describes a joint in a template topology. |
| [_BDA_TS_SELECTORINFO structure](..\bdatypes\ns-bdatypes-_bda_ts_selectorinfo.md) | . |
| [_BDA_TS_SELECTORINFO_ISDBS_EXT structure](..\bdatypes\ns-bdatypes-_bda_ts_selectorinfo_isdbs_ext.md) | . |
| [_BDA_TUNER_DIAGNOSTICS structure](..\bdatypes\ns-bdatypes-_bda_tuner_diagnostics.md) | . |
| [_BDA_TUNER_TUNERSTATE structure](..\bdatypes\ns-bdatypes-_bda_tuner_tunerstate.md) | . |
| [_BDA_USERACTIVITY_INTERVAL structure](..\bdatypes\ns-bdatypes-_bda_useractivity_interval.md) | . |
| [_BDA_WMDRMTUNER_PIDPROTECTION structure](..\bdatypes\ns-bdatypes-_bda_wmdrmtuner_pidprotection.md) | . |
| [_BDA_WMDRMTUNER_PURCHASEENTITLEMENT structure](..\bdatypes\ns-bdatypes-_bda_wmdrmtuner_purchaseentitlement.md) | . |
| [_BDA_WMDRM_KEYINFOLIST structure](..\bdatypes\ns-bdatypes-_bda_wmdrm_keyinfolist.md) | . |
| [_BDA_WMDRM_RENEWLICENSE structure](..\bdatypes\ns-bdatypes-_bda_wmdrm_renewlicense.md) | . |
| [_BDA_WMDRM_STATUS structure](..\bdatypes\ns-bdatypes-_bda_wmdrm_status.md) | . |
| [_BUS_INTERFACE_SWENUM structure](..\swenum\ns-swenum-_bus_interface_swenum.md) | The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface. |
| [_CIP_HDR1 structure](..\avcstrm\ns-avcstrm-_cip_hdr1.md) | The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair). |
| [_CIP_HDR2_FDF structure](..\avcstrm\ns-avcstrm-_cip_hdr2_fdf.md) | The CIP_HDR2_FDF structure describes the second quadlet of a CIP header pair. |
| [_CIP_HDR2_MPEGTS structure](..\avcstrm\ns-avcstrm-_cip_hdr2_mpegts.md) | The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream. |
| [_CIP_HDR2_SYT structure](..\avcstrm\ns-avcstrm-_cip_hdr2_syt.md) | The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream. |
| [_DVINFO structure](..\avcstrm\ns-avcstrm-_dvinfo.md) | The DVINFO structure describes a DV stream format including its default streaming source information and stream control information. |
| [_HW_CLOCK_OBJECT structure](..\strmini\ns-strmini-_hw_clock_object.md) | The HW_CLOCK_OBJECT structure describes the clock associated with a stream. |
| [_HW_EVENT_DESCRIPTOR structure](..\strmini\ns-strmini-_hw_event_descriptor.md) | When the class driver calls one of the minidriver's StrMiniEvent routines, it passes a pointer to an HW_EVENT_DESCRIPTOR structure to describe the event as enabled or disabled. |
| [_HW_STREAM_DESCRIPTOR structure](..\strmini\ns-strmini-_hw_stream_descriptor.md) | The minidriver uses the HW_STREAM_DESCRIPTOR structure to return stream information to the stream class driver. |
| [_HW_STREAM_HEADER structure](..\strmini\ns-strmini-_hw_stream_header.md) | The HW_STREAM_HEADER structure describes the kernel streaming semantics supported by the minidriver as a whole, as part of a HW_STREAM_DESCRIPTOR structure. |
| [_HW_STREAM_INFORMATION structure](..\strmini\ns-strmini-_hw_stream_information.md) | The HW_STREAM_INFORMATION structure describes the kernel streaming semantics supported by individual streams, as part of an HW_STREAM_DESCRIPTOR structure. |
| [_HW_STREAM_OBJECT structure](..\strmini\ns-strmini-_hw_stream_object.md) | HW_STREAM_OBJECT describes an instance of a minidriver stream. |
| [_HW_STREAM_REQUEST_BLOCK structure](..\strmini\ns-strmini-_hw_stream_request_block.md) | The stream class driver uses the HW_STREAM_REQUEST_BLOCK structure to pass information to and from the minidriver, using minidriver provided callbacks. |
| [_HW_TIME_CONTEXT structure](..\strmini\ns-strmini-_hw_time_context.md) | The class driver passes an HW_TIME_CONTEXT structure as a parameter to be filled in by a stream's StrMiniClock routine, or returns a completed HW_TIME_CONTEXT structure when it responds to a StreamClassQueryMasterClock or StreamClassQueryMasterClockSync request. |
| [_KSALLOCATOR_DISPATCH structure](..\ks\ns-ks-_ksallocator_dispatch.md) | The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator. |
| [_KSCAMERA_EXTENDEDPROP_PROFILE structure](..\ksmedia\ns-ksmedia-_kscamera_extendedprop_profile.md) | The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE. |
| [_KSCAMERA_PROFILE_CONCURRENCYINFO structure](..\ksmedia\ns-ksmedia-_kscamera_profile_concurrencyinfo.md) | An array of KSCAMERA_PROFILE_CONCURRENCYINFO structures form the Camera.Concurrency parameter of the KSDEVICE_PROFILE_INFO structure (whose array size is specified by Camera.CountOfConcurrency parameter) indicating which profiles the profile identified in the KSCAMERA_PROFILE_INFO structure may run simultaneously on different cameras. |
| [_KSCAMERA_PROFILE_INFO structure](..\ksmedia\ns-ksmedia-_kscamera_profile_info.md) | The KSCAMERA_PROFILE_INFO structure is used to uniquely identify a given profile. |
| [_KSCAMERA_PROFILE_MEDIAINFO structure](..\ksmedia\ns-ksmedia-_kscamera_profile_mediainfo.md) | This structure contains the relevant media type information presented for each camera profile. |
| [_KSCAMERA_PROFILE_PININFO structure](..\ksmedia\ns-ksmedia-_kscamera_profile_pininfo.md) | This structure specifies the available list of media types for each of the camera driver pins. |
| [_KSCLOCK_DISPATCH structure](..\ks\ns-ks-_ksclock_dispatch.md) | The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object. |
| [_KSDEVICE structure](..\ks\ns-ks-_ksdevice.md) | The KSDEVICE structure describes a WDM functional device that is managed by AVStream. |
| [_KSDEVICE_DESCRIPTOR structure](..\ks\ns-ks-_ksdevice_descriptor.md) | The KSDEVICE_DESCRIPTOR structure describes the characteristics of a particular device. |
| [_KSDEVICE_DISPATCH structure](..\ks\ns-ks-_ksdevice_dispatch.md) | The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events. |
| [_KSDEVICE_PROFILE_INFO structure](..\ksmedia\ns-ksmedia-_ksdevice_profile_info.md) | The KSDEVICE_PROFILE_INFO is a generic structure designed to handle profile information for various device types. |
| [_KSDEVICE_THERMAL_DISPATCH structure](..\ks\ns-ks-_ksdevice_thermal_dispatch.md) | The KSDEVICE_THERMAL_DISPATCH structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces. |
| [_KSEVENT_ENTRY structure](..\ks\ns-ks-_ksevent_entry.md) | The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered. |
| [_KSFILTER structure](..\ks\ns-ks-_ksfilter.md) | The KSFILTER structure describes an instantiated filter. |
| [_KSFILTERFACTORY structure](..\ks\ns-ks-_ksfilterfactory.md) | The KSFILTERFACTORY structure represents a filter factory. |
| [_KSFILTER_DESCRIPTOR structure](..\ks\ns-ks-_ksfilter_descriptor.md) | The KSFILTER_DESCRIPTOR structure describes the characteristics of a filter created by a given filter factory. |
| [_KSFILTER_DISPATCH structure](..\ks\ns-ks-_ksfilter_dispatch.md) | The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type. |
| [_KSGATE structure](..\ks\ns-ks-_ksgate.md) | The KSGATE structure describes an AVStream gate object. |
| [_KSMAPPING structure](..\ks\ns-ks-_ksmapping.md) | The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations. |
| [_KSMPEGVID_RECT structure](..\ksmedia\ns-ksmedia-_ksmpegvid_rect.md) | KSMPEGVID_RECT structure |
| [_KSM_BDA_PIN structure](..\bdamedia\ns-bdamedia-_ksm_bda_pin.md) | The KSM_BDA_PIN structure describes a method request to create or delete a pin factory for a filter. |
| [_KSM_BDA_PIN_PAIR structure](..\bdamedia\ns-bdamedia-_ksm_bda_pin_pair.md) | The KSM_BDA_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins. |
| [_KSM_PIN structure](..\bdasup\ns-bdasup-_ksm_pin.md) | The KSM_PIN structure describes a method request to create or delete a pin factory for a filter. |
| [_KSM_PIN_PAIR structure](..\bdasup\ns-bdasup-_ksm_pin_pair.md) | The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins. |
| [_KSNODE_DESCRIPTOR structure](..\ks\ns-ks-_ksnode_descriptor.md) | The KSNODE_DESCRIPTOR structure describes a topology node within a filter. |
| [_KSPIN structure](..\ks\ns-ks-_kspin.md) | The KSPIN structure describes an instantiated pin. |
| [_KSPIN_DESCRIPTOR_EX structure](..\ks\ns-ks-_kspin_descriptor_ex.md) | The KSPIN_DESCRIPTOR_EX structure describes the characteristics of a pin type on a given filter type. |
| [_KSPIN_DISPATCH structure](..\ks\ns-ks-_kspin_dispatch.md) | The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events. |
| [_KSPROCESSPIN structure](..\ks\ns-ks-_ksprocesspin.md) | The KSPROCESSPIN structure describes the process state of a specific pin. |
| [_KSPROCESSPIN_INDEXENTRY structure](..\ks\ns-ks-_ksprocesspin_indexentry.md) | The KSPROCESSPIN_INDEXENTRY structure is used in Filter-Centric Processing to bring together all of the input and output pins in one context. |
| [_KSPROPERTY_GRAPHMANAGER_INTERFACE structure](..\ks\ns-ks-_ksproperty_graphmanager_interface.md) | . |
| [_KSPROPERTY_SPHLI structure](..\ksmedia\ns-ksmedia-_ksproperty_sphli.md) | The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed. |
| [_KSPROPERTY_SPPAL structure](..\ksmedia\ns-ksmedia-_ksproperty_sppal.md) | The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display. |
| [_KSP_BDA_NODE_PIN structure](..\bdamedia\ns-bdamedia-_ksp_bda_node_pin.md) | The KSP_BDA_NODE_PIN structure describes a property request to retrieve the controlling pin for a node. |
| [_KSSTREAM_POINTER structure](..\ks\ns-ks-_ksstream_pointer.md) | The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream. |
| [_KSSTREAM_POINTER_OFFSET structure](..\ks\ns-ks-_ksstream_pointer_offset.md) | The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame. |
| [_KSSTREAM_SEGMENT structure](..\ksproxy\ns-ksproxy-_ksstream_segment.md) | The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream. |
| [_KS_COLCON structure](..\ksmedia\ns-ksmedia-_ks_colcon.md) | The KS_COLCON structure is used to describe color and contrast settings. |
| [_KS_COPY_MACROVISION structure](..\ksmedia\ns-ksmedia-_ks_copy_macrovision.md) | The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream. |
| [_KS_DVDCOPY_BUSKEY structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_buskey.md) | The KS_DVDCOPY_BUSKEY structure is used to describe the bus key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_CHLGKEY structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_chlgkey.md) | The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_DISCKEY structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_disckey.md) | The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process. |
| [_KS_DVDCOPY_REGION structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_region.md) | The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions. |
| [_KS_DVDCOPY_SET_COPY_STATE structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_set_copy_state.md) | The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream. |
| [_KS_DVDCOPY_TITLEKEY structure](..\ksmedia\ns-ksmedia-_ks_dvdcopy_titlekey.md) | The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process. |
| [_KS_DVD_YCrCb structure](..\ksmedia\ns-ksmedia-_ks_dvd_ycrcb.md) | The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace. |
| [_KS_DVD_YUV structure](..\ksmedia\ns-ksmedia-_ks_dvd_yuv.md) | The KS_DVD_YUV structure is used to describe a color in the YUV colorspace. |
| [_KS_VIDEO_STREAM_CONFIG_CAPS structure](..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md) | The KS_VIDEO_STREAM_CONFIG_CAPS structure describes the configuration and capabilities of a video stream, including analog video standard (for example, NTSC, PAL or SECAM), scaling, and cropping capabilities; minimum and maximum frame rates; and minimum and maximum data rates. |
| [_MF_MDL_SHARED_PAYLOAD_KEY structure](..\ks\ns-ks-_mf_mdl_shared_payload_key.md) | This union is used internally by the operating system. |
| [_MPEG2_TRANSPORT_STRIDE structure](..\bdatypes\ns-bdatypes-_mpeg2_transport_stride.md) | The MPEG2_TRANSPORT_STRIDE structure describes the format block of the MPEG2 transport stride. |
| [_PIPE_DIMENSIONS structure](..\ksproxy\ns-ksproxy-_pipe_dimensions.md) | The PIPE_DIMENSIONS structure is for proxy use and not recommended for application use. PIPE_DIMENSIONS contains information that describes the compression/expansion ratio of frames on various pins related to a pipe. |
| [_PIPE_TERMINATION structure](..\ksproxy\ns-ksproxy-_pipe_termination.md) | The PIPE_TERMINATION structure is for proxy use and not recommended for application use. PIPE_TERMINATION contains information that describes the pin terminator of a pipe. |
| [_STREAM_DATA_INTERSECT_INFO structure](..\strmini\ns-strmini-_stream_data_intersect_info.md) | STREAM_DATA_INTERSECT_INFO describes the parameters of a data intersection operation. |
| [_STREAM_METHOD_DESCRIPTOR structure](..\strmini\ns-strmini-_stream_method_descriptor.md) | . |
| [_STREAM_PROPERTY_DESCRIPTOR structure](..\strmini\ns-strmini-_stream_property_descriptor.md) | STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver. |
| [_STREAM_TIME_REFERENCE structure](..\strmini\ns-strmini-_stream_time_reference.md) | . |
| [_SWENUM_INSTALL_INTERFACE structure](..\swenum\ns-swenum-_swenum_install_interface.md) | The SWENUM_INSTALL_INTERFACE structure describes a specific demand-load bus enumerator object interface to install. |
| [_USBCAMD_DEVICE_DATA structure](..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md) | This structure is obsolete and is provided to maintain backward compatibility with the original USBCAMD. |
| [_USBCAMD_DEVICE_DATA2 structure](..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md) | The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls. |
| [_pipe_config_descriptor structure](..\usbcamdi\ns-usbcamdi-_pipe_config_descriptor.md) | The USBCAMD_Pipe_Config_Descriptor structure describes the association between pipes and streams. |
| [_timecode structure](..\ksmedia\ns-ksmedia-_timecode.md) | The TIMECODE union describes a timecode from an external device. This structure is no longer used. |
| [tagBDA_TRANSPORT_INFO structure](..\bdamedia\ns-bdamedia-tagbda_transport_info.md) | The BDA_TRANSPORT_INFO structure describes formatting for a stream connection. |
| [tagDEVCAPS structure](..\ksmedia\ns-ksmedia-tagdevcaps.md) | The DEVCAPS structure describes the capabilities of an external device. |
| [tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_cameraoffset.md) | The KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure contains the parameters for the Camera Angle Offset Control property. |
| [tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_evcompensation.md) | The EV Compensation Control provides for exposure control that is adjusted by increments of EV compensation steps. |
| [tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_fieldofview.md) | The Field of View Control property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position. |
| [tagKSCAMERA_EXTENDEDPROP_HEADER structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_header.md) | The KSCAMERA_EXTENDEDPROP_HEADER structure is the payload header for an extend control property. |
| [tagKSCAMERA_EXTENDEDPROP_METADATAINFO structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_metadatainfo.md) | This structure represents the metadata information for the extended property control. |
| [tagKSCAMERA_EXTENDEDPROP_PHOTOMODE structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_photomode.md) | The KSCAMERA_EXTENDEDPROP_PHOTOMODE structure contains the property data for the history frame counts in photo mode. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_configcaps.md) | This structure contains the capabilities for an ROI control. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_configcapsheader.md) | This structure contains the header information for ROI capabilities. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_exposure.md) | This structure contains the ROI info structure for exposure. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_FOCUS structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_focus.md) | This structure contains the ROI info structure for focus. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_INFO structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_info.md) | This structure contains information about an ROI. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrol.md) | This structure contains information for an ROI ISP control. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrolheader.md) | This structure contains the header information for ROI ISP controls. |
| [tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_whitebalance.md) | This structure contains the ROI info structure for white balance. |
| [tagKSCAMERA_EXTENDEDPROP_VALUE structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_value.md) | The KSCAMERA_EXTENDEDPROP_VALUE structure is a data type union used to express an extended property value. |
| [tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure](..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_videoprocsetting.md) | The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode. |
| [tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES structure](..\ksmedia\ns-ksmedia-tagkscamera_maxvideofps_forphotores.md) | The KSCAMERA_MAXVIDEOFPS_FORPHOTORES structure contains the property data for maximum frame rate at a particular resolution for a camera supporting preview and capture. |
| [tagKSCAMERA_METADATA_ITEMHEADER structure](..\ksmedia\ns-ksmedia-tagkscamera_metadata_itemheader.md) | This structure contains the metadata header information that is filled by the camera driver. |
| [tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure](..\ksmedia\ns-ksmedia-tagkscamera_metadata_photoconfirmation.md) | This structure contains the photo confirmation metadata information that is filled by the camera driver. |
| [tagKS_AMVPDATAINFO structure](..\ksmedia\ns-ksmedia-tagks_amvpdatainfo.md) | The KS_AMVPDATAINFO structure is used to describe the properties of a video port. |
| [tagKS_AMVPDIMINFO structure](..\ksmedia\ns-ksmedia-tagks_amvpdiminfo.md) | The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port. |
| [tagKS_AMVPSIZE structure](..\ksmedia\ns-ksmedia-tagks_amvpsize.md) | The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height). |
| [tagKS_AnalogVideoInfo structure](..\ksmedia\ns-ksmedia-tagks_analogvideoinfo.md) | The KS_ANALOGVIDEOINFO structure describes an analog video stream. |
| [tagKS_BDA_FRAME_INFO structure](..\bdatypes\ns-bdatypes-tagks_bda_frame_info.md) | The KS_BDA_FRAME_INFO structure describes BDA extensions to the KSSTREAM_HEADER structure, which describes a packet of data to be read from or written to a streaming driver pin. |
| [tagKS_BITMAPINFOHEADER structure](..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md) | The KS_BITMAPINFOHEADER structure describes details about the video stream, such as image dimensions and pixel depth. |
| [tagKS_DATAFORMAT_DV_AVC structure](..\avcstrm\ns-avcstrm-tagks_dataformat_dv_avc.md) | The KS_DATAFORMAT_DV_AVC structure stores the data format for an AV/C digital video connection. |
| [tagKS_DATAFORMAT_H264VIDEOINFO structure](..\ksmedia\ns-ksmedia-tagks_dataformat_h264videoinfo.md) | The KS_DATAFORMAT_H264VIDEOINFO structure describes the data formats range available for a stream. |
| [tagKS_DATAFORMAT_IMAGEINFO structure](..\ksmedia\ns-ksmedia-tagks_dataformat_imageinfo.md) | Specifies an image data format that is used for an independent image pin (or stream). |
| [tagKS_DATAFORMAT_MPEG2TS_AVC structure](..\avcstrm\ns-avcstrm-tagks_dataformat_mpeg2ts_avc.md) | The KS_DATAFORMAT_MPEG2TS_AVC structure stores the data format for an AV/C MPEG2 connection. |
| [tagKS_DATAFORMAT_VBIINFOHEADER structure](..\ksmedia\ns-ksmedia-tagks_dataformat_vbiinfoheader.md) | The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream. |
| [tagKS_DATAFORMAT_VIDEOINFOHEADER structure](..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md) | The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings. |
| [tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure](..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader2.md) | The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave. |
| [tagKS_DATAFORMAT_VIDEOINFO_PALETTE structure](..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfo_palette.md) | The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information. |
| [tagKS_DATARANGE_ANALOGVIDEO structure](..\ksmedia\ns-ksmedia-tagks_datarange_analogvideo.md) | The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream. |
| [tagKS_DATARANGE_BDA_ANTENNA structure](..\bdamedia\ns-bdamedia-tagks_datarange_bda_antenna.md) | The KS_DATARANGE_BDA_ANTENNA structure describes a range of data formats for a BDA antenna stream. |
| [tagKS_DATARANGE_BDA_TRANSPORT structure](..\bdamedia\ns-bdamedia-tagks_datarange_bda_transport.md) | The KS_DATARANGE_BDA_TRANSPORT structure describes a range of data formats for a BDA transport stream. |
| [tagKS_DATARANGE_DVVIDEO structure](..\avcstrm\ns-avcstrm-tagks_datarange_dvvideo.md) | The KS_DATARANGE_DV_AVC structure stores a range of digital video formats. |
| [tagKS_DATARANGE_DV_AVC structure](..\avcstrm\ns-avcstrm-tagks_datarange_dv_avc.md) | The KS_DATARANGE_DV_AVC structure stores a range of AV/C digital video formats. |
| [tagKS_DATARANGE_H264_VIDEO structure](..\ksmedia\ns-ksmedia-tagks_datarange_h264_video.md) | The KS_DATARANGE_H264_VIDEO structure describes the range of MPEG-2 video formats available for a stream. |
| [tagKS_DATARANGE_IMAGE structure](..\ksmedia\ns-ksmedia-tagks_datarange_image.md) | Specifies an image data range that is used in the KSPIN_DESCRIPTOR structure that describes a pin (or stream). |
| [tagKS_DATARANGE_MPEG1_VIDEO structure](..\ksmedia\ns-ksmedia-tagks_datarange_mpeg1_video.md) | The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream. |
| [tagKS_DATARANGE_MPEG2TS_AVC structure](..\avcstrm\ns-avcstrm-tagks_datarange_mpeg2ts_avc.md) | The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats. |
| [tagKS_DATARANGE_MPEG2_VIDEO structure](..\ksmedia\ns-ksmedia-tagks_datarange_mpeg2_video.md) | The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream. |
| [tagKS_DATARANGE_VIDEO structure](..\ksmedia\ns-ksmedia-tagks_datarange_video.md) | The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings. |
| [tagKS_DATARANGE_VIDEO2 structure](..\ksmedia\ns-ksmedia-tagks_datarange_video2.md) | The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings. |
| [tagKS_DATARANGE_VIDEO_PALETTE structure](..\ksmedia\ns-ksmedia-tagks_datarange_video_palette.md) | The KS_DATARANGE_VIDEO_PALETTE structure describes a stream and its color capabilities. |
| [tagKS_DATARANGE_VIDEO_VBI structure](..\ksmedia\ns-ksmedia-tagks_datarange_video_vbi.md) | The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data. |
| [tagKS_FRAME_INFO structure](..\ksmedia\ns-ksmedia-tagks_frame_info.md) | The KS_FRAME_INFO structure extends the KSSTREAM_HEADER structure for video streams. |
| [tagKS_H264VIDEOINFO structure](..\ksmedia\ns-ksmedia-tagks_h264videoinfo.md) | The KS_H264VIDEOINFO describes the device capabilities that apply to the current media type. |
| [tagKS_MPEAUDIOINFO structure](..\ksmedia\ns-ksmedia-tagks_mpeaudioinfo.md) | The KS_MPEGAUDIOINFO structure describes an MPEG audio stream. |
| [tagKS_MPEG1VIDEOINFO structure](..\ksmedia\ns-ksmedia-tagks_mpeg1videoinfo.md) | The KS_MPEG1VIDEOINFO structure describes an MPEG-1 video stream. |
| [tagKS_MPEGVIDEOINFO2 structure](..\ksmedia\ns-ksmedia-tagks_mpegvideoinfo2.md) | The KS_MPEGVIDEOINFO2 structure describes an MPEG-2 video stream, including bob or weave settings. |
| [tagKS_RGBQUAD structure](..\ksmedia\ns-ksmedia-tagks_rgbquad.md) | The KS_RGBQUAD structure describes a color consisting of relative intensities of red, green, and blue, ranging from 0 to 255 (0x0 to 0xff). |
| [tagKS_TVTUNER_CHANGE_INFO structure](..\ksmedia\ns-ksmedia-tagks_tvtuner_change_info.md) | The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel. |
| [tagKS_VBIINFOHEADER structure](..\ksmedia\ns-ksmedia-tagks_vbiinfoheader.md) | The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams. |
| [tagKS_VBI_FRAME_INFO structure](..\ksmedia\ns-ksmedia-tagks_vbi_frame_info.md) | The KS_VBI_FRAME_INFO structure extends the KSSTREAM_HEADER structure for vertical blanking interval (VBI) streams. |
| [tagKS_VIDEOINFO structure](..\ksmedia\ns-ksmedia-tagks_videoinfo.md) | The KS_VIDEOINFO structure describes the bitmap and color information for a video stream. |
| [tagKS_VIDEOINFOHEADER structure](..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md) | The KS_VIDEOINFOHEADER structure describes the bitmap and color information for a video stream. |
| [tagKS_VIDEOINFOHEADER2 structure](..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md) | The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio. |
| [tagTIMECODE_SAMPLE structure](..\ksmedia\ns-ksmedia-tagtimecode_sample.md) | The TIMECODE_SAMPLE structure describes a complete timecode. |
| [tagTRANSPORTAUDIOPARMS structure](..\ksmedia\ns-ksmedia-tagtransportaudioparms.md) | The TRANSPORTAUDIOPARMS structure is defined but not used. |
| [tagTRANSPORTBASICPARMS structure](..\ksmedia\ns-ksmedia-tagtransportbasicparms.md) | The TRANSPORTBASICPARMS structure is defined but not used. |
| [tagTRANSPORTSTATUS structure](..\ksmedia\ns-ksmedia-tagtransportstatus.md) | The TRANSPORTSTATUS structure describes the current transport status. |
| [tagTRANSPORTVIDEOPARMS structure](..\ksmedia\ns-ksmedia-tagtransportvideoparms.md) | The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future. |
| [tag_KS_TRUECOLORINFO structure](..\ksmedia\ns-ksmedia-tag_ks_truecolorinfo.md) | The KS_TRUECOLORINFO structure describes color palette and bitmask information for video images that also contain a palette. |
| [tag_video_configure_parms structure](..\msviddrv\ns-msviddrv-tag_video_configure_parms.md) | . |
| [tag_video_geterrortext_parms structure](..\msviddrv\ns-msviddrv-tag_video_geterrortext_parms.md) | . |
| [tag_video_open_parms structure](..\msviddrv\ns-msviddrv-tag_video_open_parms.md) | . |
| [tag_video_stream_init_parms structure](..\msviddrv\ns-msviddrv-tag_video_stream_init_parms.md) | . |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration](..\ksmedia\ne-ksmedia-pcapture_memory_allocation_flags.md) | The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data. |
| [*PKSPIN_COMMUNICATION enumeration](..\ks\ne-ks-pkspin_communication.md) | . |
| [*PKSPIN_DATAFLOW enumeration](..\ks\ne-ks-pkspin_dataflow.md) | An instance of the KSPIN_DATAFLOW enumeration is returned by KSPROPERTY_PIN_DATAFLOW. |
| [*PKSSTATE enumeration](..\ks\ne-ks-pksstate.md) | The KSSTATE enumeration lists possible states of a kernel streaming object. |
| [FRAMING_CACHE_OPS enumeration](..\ksproxy\ne-ksproxy-framing_cache_ops.md) | . |
| [FRAMING_PROP enumeration](..\ksproxy\ne-ksproxy-framing_prop.md) | . |
| [KSALLOCATORMODE enumeration](..\ksproxy\ne-ksproxy-ksallocatormode.md) | . |
| [KSCAMERA_EXTENDEDPROP_FOCUSSTATE enumeration](..\ksmedia\ne-ksmedia-kscamera_extendedprop_focusstate.md) | This enumeration contains the focus states. |
| [KSCAMERA_EXTENDEDPROP_MetadataAlignment enumeration](..\ksmedia\ne-ksmedia-kscamera_extendedprop_metadataalignment.md) | This enumeration contains identifiers for the metadata alignment. |
| [KSCAMERA_EXTENDEDPROP_ROITYPE enumeration](..\ksmedia\ne-ksmedia-kscamera_extendedprop_roitype.md) | This enumeration contains the ROI types. |
| [KSCAMERA_MetadataId enumeration](..\ksmedia\ne-ksmedia-kscamera_metadataid.md) | This enumeration contains identifiers for a metadata item. |
| [KSCAMERA_PERFRAMESETTING_ITEM_TYPE enumeration](..\ksmedia\ne-ksmedia-kscamera_perframesetting_item_type.md) | This enumeration contains the different item types for the per-frame settings DDI. |
| [KSCOMPLETION_INVOCATION enumeration](..\ks\ne-ks-kscompletion_invocation.md) | . |
| [KSDEGRADE_STANDARD enumeration](..\ks\ne-ks-ksdegrade_standard.md) | The KSDEGRADE_STANDARD enumeration lists different types of degradation. |
| [KSDEVICE_THERMAL_STATE enumeration](..\ks\ne-ks-ksdevice_thermal_state.md) | A KS-defined enumeration for thermal state changes. |
| [KSEVENTS_LOCKTYPE enumeration](..\ks\ne-ks-ksevents_locktype.md) | The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with EventFlags in several event-set helper functions. |
| [KSEVENT_CAMERACONTROL enumeration](..\ksmedia\ne-ksmedia-ksevent_cameracontrol.md) | Specifies camera control event notifications that the driver generates to indicate that an operation has been completed or canceled. |
| [KSEVENT_CAMERAEVENT enumeration](..\ksmedia\ne-ksmedia-ksevent_cameraevent.md) | KSEVENT_CAMERAEVENT enumerates a kernel streaming event set that can be used by the pipeline to enable or disable camera event notifications from the driver. |
| [KSEVENT_CLOCK_POSITION enumeration](..\ks\ne-ks-ksevent_clock_position.md) | . |
| [KSEVENT_CONNECTION enumeration](..\ks\ne-ks-ksevent_connection.md) | . |
| [KSEVENT_DEVICE enumeration](..\ks\ne-ks-ksevent_device.md) | Specifies event notifications that the driver generates to indicate that a device has been lost or preempted. |
| [KSEVENT_PINCAPS_CHANGENOTIFICATIONS enumeration](..\ks\ne-ks-ksevent_pincaps_changenotifications.md) | . |
| [KSEVENT_STREAMALLOCATOR enumeration](..\ks\ne-ks-ksevent_streamallocator.md) | . |
| [KSEVENT_VOLUMELIMIT enumeration](..\ks\ne-ks-ksevent_volumelimit.md) | . |
| [KSINTERFACE_FILEIO enumeration](..\ks\ne-ks-ksinterface_fileio.md) | . |
| [KSINTERFACE_STANDARD enumeration](..\ks\ne-ks-ksinterface_standard.md) | . |
| [KSIOOPERATION enumeration](..\ksproxy\ne-ksproxy-ksiooperation.md) | . |
| [KSIRP_REMOVAL_OPERATION enumeration](..\ks\ne-ks-ksirp_removal_operation.md) | . |
| [KSLIST_ENTRY_LOCATION enumeration](..\ks\ne-ks-kslist_entry_location.md) | . |
| [KSMETHOD_STREAMALLOCATOR enumeration](..\ks\ne-ks-ksmethod_streamallocator.md) | . |
| [KSMETHOD_STREAMIO enumeration](..\ks\ne-ks-ksmethod_streamio.md) | . |
| [KSOBJECTTYPE enumeration](..\ks\ne-ks-ksobjecttype.md) | The KSOBJECTTYPE enumeration lists different types of kernel streaming objects. |
| [KSPEEKOPERATION enumeration](..\ksproxy\ne-ksproxy-kspeekoperation.md) | . |
| [KSPIN_MDL_CACHING_EVENT enumeration](..\ks\ne-ks-kspin_mdl_caching_event.md) | This enumeration is used internally by the operating system. |
| [KSPPROPERTY_ALLOCATOR_MDLCACHING enumeration](..\ks\ne-ks-kspproperty_allocator_mdlcaching.md) | This enumeration is used internally by the operating system. |
| [KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_extended_property.md) | This enumeration contains extended camera controls. |
| [KSPROPERTY_CAMERACONTROL_FLASH enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_flash.md) | Used to specify camera flash control. |
| [KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_image_pin_capability.md) | Used to identify whether the camera's image pin and record pin are mutually exclusive. If they are mutually exclusive, then when the record pin is active, the image pin cannot be active, and vice-versa. |
| [KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_perframesetting_property.md) | This enumeration contains the property IDs defined for the per-frame property set. |
| [KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_region_of_interest.md) | Used to specify a camera region of interest. |
| [KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE enumeration](..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_video_stabilization_mode.md) | Used to specify camera video stabilization. |
| [KSPROPERTY_CLOCK enumeration](..\ks\ne-ks-ksproperty_clock.md) | . |
| [KSPROPERTY_CONNECTION enumeration](..\ks\ne-ks-ksproperty_connection.md) | . |
| [KSPROPERTY_GENERAL enumeration](..\ks\ne-ks-ksproperty_general.md) | . |
| [KSPROPERTY_GM enumeration](..\ks\ne-ks-ksproperty_gm.md) | . |
| [KSPROPERTY_MEDIASEEKING enumeration](..\ks\ne-ks-ksproperty_mediaseeking.md) | . |
| [KSPROPERTY_PIN enumeration](..\ks\ne-ks-ksproperty_pin.md) | . |
| [KSPROPERTY_QUALITY enumeration](..\ks\ne-ks-ksproperty_quality.md) | . |
| [KSPROPERTY_SERVICE enumeration](..\ksi\ne-ksi-ksproperty_service.md) | . |
| [KSPROPERTY_STREAM enumeration](..\ks\ne-ks-ksproperty_stream.md) | . |
| [KSPROPERTY_STREAMALLOCATOR enumeration](..\ks\ne-ks-ksproperty_streamallocator.md) | . |
| [KSPROPERTY_STREAMINTERFACE enumeration](..\ks\ne-ks-ksproperty_streaminterface.md) | . |
| [KSPROPERTY_TOPOLOGY enumeration](..\ks\ne-ks-ksproperty_topology.md) | . |
| [KSRESET enumeration](..\ks\ne-ks-ksreset.md) | . |
| [KSSTACK_USE enumeration](..\ks\ne-ks-ksstack_use.md) | . |
| [KSSTREAM_POINTER_STATE enumeration](..\ks\ne-ks-ksstream_pointer_state.md) | . |
| [KSTARGET_STATE enumeration](..\ks\ne-ks-kstarget_state.md) | . |
| [KS_AMPixAspectRatio enumeration](..\ksmedia\ne-ksmedia-ks_ampixaspectratio.md) | The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720 480 NTSC video signal or a 720 × 576 PAL video signal. |
| [KS_AMVP_MODE enumeration](..\ksmedia\ne-ksmedia-ks_amvp_mode.md) | The KS_AMVP_MODE enumeration defines video port display modes. |
| [KS_AMVP_SELECTFORMATBY enumeration](..\ksmedia\ne-ksmedia-ks_amvp_selectformatby.md) | The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format. |
| [KS_AnalogVideoStandard enumeration](..\ksmedia\ne-ksmedia-ks_analogvideostandard.md) | The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide. |
| [KS_CameraControlAsyncOperation enumeration](..\ksmedia\ne-ksmedia-ks_cameracontrolasyncoperation.md) | Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. |
| [KS_CompressionCaps enumeration](..\ksmedia\ne-ksmedia-ks_compressioncaps.md) | The KS_CompressionCaps enumeration defines compression capabilities of a device. |
| [KS_DVDCOPYSTATE enumeration](..\ksmedia\ne-ksmedia-ks_dvdcopystate.md) | The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence. |
| [KS_LogicalMemoryType enumeration](..\ksproxy\ne-ksproxy-ks_logicalmemorytype.md) | . |
| [KS_MPEG2Level enumeration](..\ksmedia\ne-ksmedia-ks_mpeg2level.md) | The KS_MPEG2Level enumeration describes MPEG-2 levels. |
| [KS_MPEG2Profile enumeration](..\ksmedia\ne-ksmedia-ks_mpeg2profile.md) | The KS_MPEG2Profile enumeration describes MPEG-2 profiles. |
| [KS_SEEKING_CAPABILITIES enumeration](..\ks\ne-ks-ks_seeking_capabilities.md) | . |
| [KS_SEEKING_FLAGS enumeration](..\ks\ne-ks-ks_seeking_flags.md) | The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the KSPROPERTY_POSITIONS structure. |
| [KS_TUNER_STRATEGY enumeration](..\ksmedia\ne-ksmedia-ks_tuner_strategy.md) | The KS_TUNER_STRATEGY enumeration defines tuning method strategies. |
| [KS_TUNER_TUNING_FLAGS enumeration](..\ksmedia\ne-ksmedia-ks_tuner_tuning_flags.md) | The KS_TUNER_TUNING_FLAGS enumeration defines tuning flags that describe the granularity of a tuning operation. |
| [KS_VIDEODECODER_FLAGS enumeration](..\ksmedia\ne-ksmedia-ks_videodecoder_flags.md) | The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities. |
| [KS_VideoControlFlags enumeration](..\ksmedia\ne-ksmedia-ks_videocontrolflags.md) | The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream. |
| [KS_VideoStreamingHints enumeration](..\ksmedia\ne-ksmedia-ks_videostreaminghints.md) | The KS_VideoStreamingHints enumeration defines video compression hints. |
| [LAMP_MODE enumeration](..\lamp\ne-lamp-lamp_mode.md) | This enumeration contains the operating modes of a lamp device. |
| [PIPE_ALLOCATOR_PLACE enumeration](..\ksproxy\ne-ksproxy-pipe_allocator_place.md) | . |
| [PIPE_STATE enumeration](..\ksproxy\ne-ksproxy-pipe_state.md) | . |
| [STREAM_BUFFER_TYPE enumeration](..\strmini\ne-strmini-stream_buffer_type.md) | This enumeration defines the buffer types for StreamClassGetPhysicalAddress. |
| [STREAM_DEBUG_LEVEL enumeration](..\strmini\ne-strmini-stream_debug_level.md) | The STREAM_DEBUG_LEVEL enumeration lists incrementally increasing levels of debugger output. |
| [TIME_FUNCTION enumeration](..\strmini\ne-strmini-time_function.md) | . |
| [VARENUM enumeration](..\ks\ne-ks-varenum.md) | . |
| [VIDEOENCODER_BITRATE_MODE enumeration](..\ksmedia\ne-ksmedia-videoencoder_bitrate_mode.md) | The VIDEOENCODER_BITRATE_MODE enumeration describes the bit rate encoding modes supported by the device. |
| [_AVCSTRM_FORMAT enumeration](..\avcstrm\ne-avcstrm-_avcstrm_format.md) | The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by avcstrm.sys. |
| [_AVCSTRM_FUNCTION enumeration](..\avcstrm\ne-avcstrm-_avcstrm_function.md) | The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the avcstrm.sys driver. |
| [_BdaLockType enumeration](..\bdamedia\ne-bdamedia-_bdalocktype.md) | The BDA_LockType enumerated type contains values that specify lock types for a signal. |
| [_KSPIN_FLAG_AVC enumeration](..\avc\ne-avc-_kspin_flag_avc.md) | The KSPIN_FLAG_AVC enumeration type is used for connection management and in the AVC_FUNCTION_GET_CONNECTINFO function code. |
| [_SRB_COMMAND enumeration](..\strmini\ne-strmini-_srb_command.md) | . |
| [_STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE enumeration](..\strmini\ne-strmini-_stream_minidriver_device_notification_type.md) | . |
| [_STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE enumeration](..\strmini\ne-strmini-_stream_minidriver_stream_notification_type.md) | . |
| [_STREAM_PRIORITY enumeration](..\strmini\ne-strmini-_stream_priority.md) | TD. |
| [_tagAVC_FUNCTION enumeration](..\avc\ne-avc-_tagavc_function.md) | The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions. |
| [_tagAvcCommandType enumeration](..\avc\ne-avc-_tagavccommandtype.md) | The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_GET_REQUEST function codes. |
| [_tagAvcResponseCode enumeration](..\avc\ne-avc-_tagavcresponsecode.md) | The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_SEND_RESPONSE function codes. |
| [_tagAvcSubunitType enumeration](..\avc\ne-avc-_tagavcsubunittype.md) | The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_AVCSTRM_CLASS IOCTL](..\avcstrm\ni-avcstrm-ioctl_avcstrm_class.md) | An AV/C subunit driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP, with the IoControlCode member set to IOCTL_AVCSTRM_CLASS, to communicate with avcstrm.sys. |
| [IOCTL_AVC_BUS_RESET IOCTL](..\avc\ni-avc-ioctl_avc_bus_reset.md) | The IOCTL_AVC_BUS_RESET I/O control code allows the caller to complete any previous IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO and IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control requests that did not use the AVC_SUBUNIT_ADDR_TRIGGERBUSRESET flag. |
| [IOCTL_AVC_CLASS IOCTL](..\avc\ni-avc-ioctl_avc_class.md) | The IOCTL_AVC_CLASS I/O control code is supported only from kernel mode, using the IRP_MJ_INTERNAL_DEVICE_CONTROL dispatch.Avc.sys supports two device interfaces, depending upon the type of instance (peer or virtual). |
| [IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO IOCTL](..\avc\ni-avc-ioctl_avc_remove_virtual_subunit_info.md) | The IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. |
| [IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO IOCTL](..\avc\ni-avc-ioctl_avc_update_virtual_subunit_info.md) | The IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. |
| [IOCTL_KS_DISABLE_EVENT IOCTL](..\ks\ni-ks-ioctl_ks_disable_event.md) | An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the IoControl parameter of a call to KsSynchronousDeviceControl. |
| [IOCTL_KS_ENABLE_EVENT IOCTL](..\ks\ni-ks-ioctl_ks_enable_event.md) | An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. |
| [IOCTL_KS_HANDSHAKE IOCTL](..\ks\ni-ks-ioctl_ks_handshake.md) | A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. |
| [IOCTL_KS_METHOD IOCTL](..\ks\ni-ks-ioctl_ks_method.md) | An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_PROPERTY IOCTL](..\ks\ni-ks-ioctl_ks_property.md) | An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_READ_STREAM IOCTL](..\ks\ni-ks-ioctl_ks_read_stream.md) | An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_RESET_STATE IOCTL](..\ks\ni-ks-ioctl_ks_reset_state.md) | An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at Acquire-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_WRITE_STREAM IOCTL](..\ks\ni-ks-ioctl_ks_write_stream.md) | An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_LAMP_GET_CAPABILITIES_COLOR IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_capabilities_color.md) | The IOCTL_LAMP_GET_CAPABILITIES_COLOR control code queries the capabilities of the lamp when the device is configured to emit color light. |
| [IOCTL_LAMP_GET_CAPABILITIES_WHITE IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_capabilities_white.md) | The IOCTL_LAMP_GET_CAPABILITIES_WHITE control code queries the capabilities of the lamp when the device is configured to emit white light. |
| [IOCTL_LAMP_GET_EMITTING_LIGHT IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_emitting_light.md) | The IOCTL_LAMP_GET_EMITTING_LIGHT control code queries if the lamp is turned on. |
| [IOCTL_LAMP_GET_INTENSITY_COLOR IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_intensity_color.md) | The IOCTL_LAMP_GET_INTENSITY_COLOR control code queries the light intensity when the lamp is configured to emit color light. |
| [IOCTL_LAMP_GET_INTENSITY_WHITE IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_intensity_white.md) | The IOCTL_LAMP_GET_INTENSITY_WHITE control code queries the light intensity when the lamp is configured to emit white light. |
| [IOCTL_LAMP_GET_MODE IOCTL](..\lamp\ni-lamp-ioctl_lamp_get_mode.md) | The IOCTL_LAMP_GET_MODE control code queries the mode with which the lamp is currently configured. |
| [IOCTL_LAMP_SET_EMITTING_LIGHT IOCTL](..\lamp\ni-lamp-ioctl_lamp_set_emitting_light.md) | The IOCTL_LAMP_SET_EMITTING_LIGHT control code turns the lamp on or off. |
| [IOCTL_LAMP_SET_INTENSITY_COLOR IOCTL](..\lamp\ni-lamp-ioctl_lamp_set_intensity_color.md) | The IOCTL_LAMP_SET_INTENSITY_COLOR control code sets the lamp to the specified light intensity. |
| [IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL](..\lamp\ni-lamp-ioctl_lamp_set_intensity_white.md) | The IOCTL_LAMP_SET_INTENSITY_WHITE control code sets the lamp to the specified light intensity. |
| [IOCTL_LAMP_SET_MODE IOCTL](..\lamp\ni-lamp-ioctl_lamp_set_mode.md) | The IOCTL_LAMP_SET_MODE control code sets the mode in which the lamp operates. |
| [IOCTL_SWENUM_GET_BUS_ID IOCTL](..\swenum\ni-swenum-ioctl_swenum_get_bus_id.md) | TBD |
| [IOCTL_SWENUM_INSTALL_INTERFACE IOCTL](..\swenum\ni-swenum-ioctl_swenum_install_interface.md) | TBD |
| [IOCTL_SWENUM_REMOVE_INTERFACE IOCTL](..\swenum\ni-swenum-ioctl_swenum_remove_interface.md) | TBD |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IKsAggregateControl interface](..\ksproxy\nn-ksproxy-iksaggregatecontrol.md) | The IKsAggregateControl interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface. |
| [IKsAllocator interface](..\ksproxy\nn-ksproxy-iksallocator.md) | TheIKsAllocator interface provides methods that control and query an allocator. IKsAllocator is for proxy use and not recommended for application use. |
| [IKsAllocatorEx interface](..\ksproxy\nn-ksproxy-iksallocatorex.md) | The IKsAllocatorEx interface is for proxy use and not recommended for application use. IKsAllocatorEx inherits all the methods of the IKsAllocator interface and extends IKsAllocator to provide methods that further control and query an allocator. |
| [IKsClockPropertySet interface](..\ksproxy\nn-ksproxy-iksclockpropertyset.md) | The IKsClockPropertySet interface provides methods that let the proxy accurately reflect time. |
| [IKsControl interface](..\ks\nn-ks-ikscontrol.md) | The IKsControl interface is a COM-style interface implemented on AVStream filters and pins. |
| [IKsControl interface](..\ksproxy\nn-ksproxy-ikscontrol.md) | The IKsControl interface provides user-mode methods that control a KS filter or KS pin. See the IKsControl AVStream COM interface for information about the user-mode equivalent of this interface. |
| [IKsDataTypeCompletion interface](..\ksproxy\nn-ksproxy-iksdatatypecompletion.md) | The IKsDataTypeCompletion interface provides a method to complete partially specified media types that are passed to the IAMStreamConfig |
| [IKsDataTypeHandler interface](..\ksproxy\nn-ksproxy-iksdatatypehandler.md) | The IKsDataTypeHandler interface provides methods that perform optional preprocessing and postprocessing of media samples. |
| [IKsDeviceFunctions interface](..\ks\nn-ks-iksdevicefunctions.md) | The IKsDeviceFunctions interface is a COM-style interface implemented on AVStream devices. This interface is available in Windows Server 2003 SP1 and later versions of Windows. |
| [IKsInterfaceHandler interface](..\ksproxy\nn-ksproxy-iksinterfacehandler.md) | The IKsInterfaceHandler interface provides methods that marshal samples into the kernel based on the KSPIN_INTERFACE structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler. |
| [IKsNotifyEvent interface](..\ksproxy\nn-ksproxy-iksnotifyevent.md) | The IKsNotifyEvent interface provides a method to cause the KS object that owns a DirectShow event to issue the event with the given parameters. |
| [IKsObject interface](..\ksproxy\nn-ksproxy-iksobject.md) | The IKsObject interface provides a method to retrieve the file handle of a KS object. |
| [IKsPin interface](..\ksproxy\nn-ksproxy-ikspin.md) | The IKsPin interface provides methods that control and retrieve information about a pin. |
| [IKsPinEx interface](..\ksproxy\nn-ksproxy-ikspinex.md) | The IKsPinEx interface inherits all the methods of the IKsPin interface and extends IKsPin to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt. |
| [IKsPinFactory interface](..\ksproxy\nn-ksproxy-ikspinfactory.md) | The IKsPinFactory interface provides a method that retrieves the identifier of a pin factory. |
| [IKsPinPipe interface](..\ksproxy\nn-ksproxy-ikspinpipe.md) | The IKsPinPipe interface is for proxy use and not recommended for application use. IKsPinPipe provides methods that control a pin pipe. |
| [IKsPropertySet interface](..\dsound\nn-dsound-ikspropertyset.md) | The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver. |
| [IKsQualityForwarder interface](..\ksproxy\nn-ksproxy-iksqualityforwarder.md) | The IKsQualityForwarder interface inherits the method of the IKsObject interface and extends IKsObject to provide a method that flushes information from a pin. |
| [IKsReferenceClock interface](..\ks\nn-ks-iksreferenceclock.md) | The IKsReferenceClock interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock. |
| [IKsTopology interface](..\ksproxy\nn-ksproxy-ikstopology.md) | The IKsTopology interface provides a method that opens topology node objects contained within a filter. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [INIT_AVCSTRM_HEADER macro](..\avcstrm\nf-avcstrm-init_avcstrm_header.md) | The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure. |
| [KSEVENT_ENTRY_IRP_STORAGE macro](..\ks\nf-ks-ksevent_entry_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_ENTRY structure stored in Irp. |
| [KSEVENT_ITEM_IRP_STORAGE macro](..\ks\nf-ks-ksevent_item_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_ITEM structure stored in Irp. |
| [KSEVENT_SET_IRP_STORAGE macro](..\ks\nf-ks-ksevent_set_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_SET structure stored in Irp. This information is initialized only for basic support requests; it is not initialized for enable requests. |
| [KSMETHOD_ITEM_IRP_STORAGE macro](..\ks\nf-ks-ksmethod_item_irp_storage.md) | This macro accesses a pointer to the relevant KSMETHOD_ITEM. Note that this pointer is only set when using KsMethodHandlerWithAllocator. |
| [KSMETHOD_SET_IRP_STORAGE macro](..\ks\nf-ks-ksmethod_set_irp_storage.md) | This macro returns a pointer to the KSMETHOD_SET in which the method is located. |
| [KSMETHOD_TYPE_IRP_STORAGE macro](..\ks\nf-ks-ksmethod_type_irp_storage.md) | This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact. |
| [KsDeleteFilterFactory macro](..\ks\nf-ks-ksdeletefilterfactory.md) | KsDeleteFilterFactory deletes a given filter factory. |
| [KsDiscard macro](..\ks\nf-ks-ksdiscard.md) | The KsDiscard macro removes a given item from an object bag. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IKsAggregateControl::KsAddAggregate method](..\ksproxy\nf-ksproxy-iksaggregatecontrol-ksaddaggregate.md) | The KsAddAggregate method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the IKsAggregateControl interface. |
| [IKsAggregateControl::KsRemoveAggregate method](..\ksproxy\nf-ksproxy-iksaggregatecontrol-ksremoveaggregate.md) | The KsRemoveAggregate method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the IKsAggregateControl interface. |
| [IKsAllocator::KsGetAllocatorHandle method](..\ksproxy\nf-ksproxy-iksallocator-ksgetallocatorhandle.md) | Retrieves a file handle to an allocator. |
| [IKsAllocator::KsGetAllocatorMode method](..\ksproxy\nf-ksproxy-iksallocator-ksgetallocatormode.md) | Returns the mode in which an allocator allocates memory. |
| [IKsAllocator::KsGetAllocatorStatus method](..\ksproxy\nf-ksproxy-iksallocator-ksgetallocatorstatus.md) | Retrieves the status of an allocator. |
| [IKsAllocator::KsSetAllocatorMode method](..\ksproxy\nf-ksproxy-iksallocator-kssetallocatormode.md) | Sets the mode in which an allocator allocates memory. |
| [IKsAllocatorEx::KsGetProperties method](..\ksproxy\nf-ksproxy-iksallocatorex-ksgetproperties.md) | Returns the properties for an allocator. |
| [IKsAllocatorEx::KsSetAllocatorHandle method](..\ksproxy\nf-ksproxy-iksallocatorex-kssetallocatorhandle.md) | Sets the handle for an allocator. |
| [IKsAllocatorEx::KsSetProperties method](..\ksproxy\nf-ksproxy-iksallocatorex-kssetproperties.md) | Sets the properties for an allocator. |
| [IKsClockPropertySet::KsGetCorrelatedPhysicalTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgetcorrelatedphysicaltime.md) | The KsGetCorrelatedPhysicalTime method retrieves the physical time and the correlated system time from the underlying clock. |
| [IKsClockPropertySet::KsGetCorrelatedTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgetcorrelatedtime.md) | The KsGetCorrelatedTime method retrieves the current time and the correlated system time from the underlying clock. |
| [IKsClockPropertySet::KsGetPhysicalTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgetphysicaltime.md) | The KsGetPhysicalTime method retrieves the physical time from the underlying clock. |
| [IKsClockPropertySet::KsGetResolution method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgetresolution.md) | The KsGetResolution method retrieves the clock resolution from the underlying clock. |
| [IKsClockPropertySet::KsGetState method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgetstate.md) | The KsGetState method retrieves the streaming state of a pin from the underlying clock. |
| [IKsClockPropertySet::KsGetTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-ksgettime.md) | The KsGetTime method retrieves the time of the underlying clock. |
| [IKsClockPropertySet::KsSetCorrelatedPhysicalTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-kssetcorrelatedphysicaltime.md) | The KsSetCorrelatedPhysicalTime method sets the physical time with the correlated system time on the underlying clock. |
| [IKsClockPropertySet::KsSetCorrelatedTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-kssetcorrelatedtime.md) | The KsSetCorrelatedTime method sets the current time with the correlated system time on the underlying clock. |
| [IKsClockPropertySet::KsSetPhysicalTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-kssetphysicaltime.md) | The KsSetPhysicalTime method sets the physical time on the underlying clock. |
| [IKsClockPropertySet::KsSetTime method](..\ksproxy\nf-ksproxy-iksclockpropertyset-kssettime.md) | The KsSetTime method sets the current time on the underlying clock. |
| [IKsControl::KsEvent method](..\ks\nf-ks-ikscontrol-ksevent.md) | The IKsControl |
| [IKsControl::KsEvent method](..\ksproxy\nf-ksproxy-ikscontrol-ksevent.md) | The KsEvent method enables or disables an event, along with any other defined support operations available on an event set. |
| [IKsControl::KsMethod method](..\ks\nf-ks-ikscontrol-ksmethod.md) | The IKsControl |
| [IKsControl::KsMethod method](..\ksproxy\nf-ksproxy-ikscontrol-ksmethod.md) | The KsMethod method sends a method to a KS object, along with any other defined support operations available on a method set. |
| [IKsControl::KsProperty method](..\ks\nf-ks-ikscontrol-ksproperty.md) | The IKsControl |
| [IKsControl::KsProperty method](..\ksproxy\nf-ksproxy-ikscontrol-ksproperty.md) | The KsProperty method sets a property or retrieves property information, along with any other defined support operations available on a property set. |
| [IKsDataTypeCompletion::KsCompleteMediaType method](..\ksproxy\nf-ksproxy-iksdatatypecompletion-kscompletemediatype.md) | The KsCompleteMediaType method completes a partially-specified media type that was first presented to the IAMStreamConfig |
| [IKsDataTypeHandler::KsCompleteIoOperation method](..\ksproxy\nf-ksproxy-iksdatatypehandler-kscompleteiooperation.md) | The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation. |
| [IKsDataTypeHandler::KsIsMediaTypeInRanges method](..\ksproxy\nf-ksproxy-iksdatatypehandler-ksismediatypeinranges.md) | The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges. |
| [IKsDataTypeHandler::KsPrepareIoOperation method](..\ksproxy\nf-ksproxy-iksdatatypehandler-ksprepareiooperation.md) | The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation. |
| [IKsDataTypeHandler::KsQueryExtendedSize method](..\ksproxy\nf-ksproxy-iksdatatypehandler-ksqueryextendedsize.md) | The KsQueryExtendedSize method retrieves extended header information required for input and output (I/O) operations. |
| [IKsDataTypeHandler::KsSetMediaType method](..\ksproxy\nf-ksproxy-iksdatatypehandler-kssetmediatype.md) | The KsSetMediaType method sets the media type for a data type handler. |
| [IKsDeviceFunctions::RegisterAdapterObjectEx method](..\ks\nf-ks-iksdevicefunctions-registeradapterobjectex.md) | The IKsDeviceFunctions |
| [IKsInterfaceHandler::KsCompleteIo method](..\ksproxy\nf-ksproxy-iksinterfacehandler-kscompleteio.md) | The KsCompleteIo method cleans up extended headers and releases media samples after input and output (I/O) complete. |
| [IKsInterfaceHandler::KsProcessMediaSamples method](..\ksproxy\nf-ksproxy-iksinterfacehandler-ksprocessmediasamples.md) | The KsProcessMediaSamples method processes media samples. |
| [IKsInterfaceHandler::KsSetPin method](..\ksproxy\nf-ksproxy-iksinterfacehandler-kssetpin.md) | The KsSetPin method informs the streaming interface handler about the pin with which to communicate when passing data. |
| [IKsNotifyEvent::KsNotifyEvent method](..\ksproxy\nf-ksproxy-iksnotifyevent-ksnotifyevent.md) | The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs. |
| [IKsObject::KsGetObjectHandle method](..\ksproxy\nf-ksproxy-iksobject-ksgetobjecthandle.md) | The KsGetObjectHandle method retrieves a file handle to a KS object. |
| [IKsPin::KsCreateSinkPinHandle method](..\ksproxy\nf-ksproxy-ikspin-kscreatesinkpinhandle.md) | The KsCreateSinkPinHandle method creates a pin handle and stores it in the KS pin object. |
| [IKsPin::KsDecrementPendingIoCount method](..\ksproxy\nf-ksproxy-ikspin-ksdecrementpendingiocount.md) | The KsDecrementPendingIoCount method decrements the number of input/output (I/O) operations that are in progress on a pin. |
| [IKsPin::KsDeliver method](..\ksproxy\nf-ksproxy-ikspin-ksdeliver.md) | The KsDeliver method delivers a media sample from an output pin to an input pin, continues an I/O operation by retrieving the next buffer from an allocator, and submits the buffer to the associated device. |
| [IKsPin::KsGetCurrentCommunication method](..\ksproxy\nf-ksproxy-ikspin-ksgetcurrentcommunication.md) | The KsGetCurrentCommunication method retrieves the current communication direction, interface, and medium of a pin. |
| [IKsPin::KsIncrementPendingIoCount method](..\ksproxy\nf-ksproxy-ikspin-ksincrementpendingiocount.md) | The KsIncrementPendingIoCount method increments the number of input/output (I/O) operations that are in progress on a pin. |
| [IKsPin::KsMediaSamplesCompleted method](..\ksproxy\nf-ksproxy-ikspin-ksmediasamplescompleted.md) | The KsMediaSamplesCompleted method informs a pin that a stream segment completed. |
| [IKsPin::KsPeekAllocator method](..\ksproxy\nf-ksproxy-ikspin-kspeekallocator.md) | The KsPeekAllocator method returns a pointer to an IMemAllocator interface for a pin's assigned allocator. |
| [IKsPin::KsPropagateAcquire method](..\ksproxy\nf-ksproxy-ikspin-kspropagateacquire.md) | The KsPropagateAcquire method directs all the pins on the filter to attain the Acquire state. |
| [IKsPin::KsQueryInterfaces method](..\ksproxy\nf-ksproxy-ikspin-ksqueryinterfaces.md) | The KsQueryInterfaces method retrieves interfaces that a pin supports. |
| [IKsPin::KsQueryMediums method](..\ksproxy\nf-ksproxy-ikspin-ksquerymediums.md) | The KsQueryMediums method retrieves mediums that a pin supports. |
| [IKsPinEx::KsNotifyError method](..\ksproxy\nf-ksproxy-ikspinex-ksnotifyerror.md) | The KsNotifyError method notifies the filter graph of an error to give the filter graph an opportunity to halt. |
| [IKsPinFactory::KsPinFactory method](..\ksproxy\nf-ksproxy-ikspinfactory-kspinfactory.md) | The KsPinFactory method retrieves the identifier of a pin factory. |
| [IKsPinPipe::KsGetConnectedPin method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetconnectedpin.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetFilterName method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetfiltername.md) | Returns the name of a filter. |
| [IKsPinPipe::KsGetPinBusCache method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetpinbuscache.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPinFramingCache method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetpinframingcache.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPinName method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetpinname.md) | Returns the name of a pin. |
| [IKsPinPipe::KsGetPipe method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetpipe.md) | Not recommended for application use. |
| [IKsPinPipe::KsGetPipeAllocatorFlag method](..\ksproxy\nf-ksproxy-ikspinpipe-ksgetpipeallocatorflag.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPinBusCache method](..\ksproxy\nf-ksproxy-ikspinpipe-kssetpinbuscache.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPinFramingCache method](..\ksproxy\nf-ksproxy-ikspinpipe-kssetpinframingcache.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPipe method](..\ksproxy\nf-ksproxy-ikspinpipe-kssetpipe.md) | Not recommended for application use. |
| [IKsPinPipe::KsSetPipeAllocatorFlag method](..\ksproxy\nf-ksproxy-ikspinpipe-kssetpipeallocatorflag.md) | Not recommended for application use. |
| [IKsPropertySet::Get method](..\ksproxy\nf-ksproxy-ikspropertyset-get.md) | The Get method retrieves a property identified by a property-set GUID and a property identifier. |
| [IKsPropertySet::QuerySupported method](..\ksproxy\nf-ksproxy-ikspropertyset-querysupported.md) | The QuerySupported method determines whether a KS object supports a property set and the type of that support. |
| [IKsPropertySet::Set method](..\dsound\nf-dsound-ikspropertyset-set.md) | The Set method sets a property identified by a property-set GUID and a property identifier. |
| [IKsPropertySet::Set method](..\ksproxy\nf-ksproxy-ikspropertyset-set.md) | The Set method sets a property identified by a property-set GUID and a property identifier. |
| [IKsQualityForwarder::KsFlushClient method](..\ksproxy\nf-ksproxy-iksqualityforwarder-ksflushclient.md) | The KsFlushClient method flushes information from a pin. |
| [IKsReferenceClock::GetCorrelatedPhysicalTime method](..\ks\nf-ks-iksreferenceclock-getcorrelatedphysicaltime.md) | The IKsReferenceClock |
| [IKsReferenceClock::GetCorrelatedTime method](..\ks\nf-ks-iksreferenceclock-getcorrelatedtime.md) | The IKsReferenceClock |
| [IKsReferenceClock::GetPhysicalTime method](..\ks\nf-ks-iksreferenceclock-getphysicaltime.md) | The IKsReferenceClock |
| [IKsReferenceClock::GetResolution method](..\ks\nf-ks-iksreferenceclock-getresolution.md) | The IKsReferenceClock |
| [IKsReferenceClock::GetState method](..\ks\nf-ks-iksreferenceclock-getstate.md) | The IKsReferenceClock |
| [IKsReferenceClock::GetTime method](..\ks\nf-ks-iksreferenceclock-gettime.md) | The IKsReferenceClock |
| [IKsTopology::CreateNodeInstance method](..\ksproxy\nf-ksproxy-ikstopology-createnodeinstance.md) | The CreateNodeInstance method requests a KS filter object to open a topology node object. |
