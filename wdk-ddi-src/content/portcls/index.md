---
UID: NA:portcls
ms.assetid: 6e1a2bb6-6b07-3266-83bb-aa08030d97d6
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Portcls.h header



This header is used by Audio. For more information, see
- [Audio](../_audio/index.md)

Portcls.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [PcAddAdapterDevice function](nf-portcls-pcaddadapterdevice.md) | The PcAddAdapterDevice function adds an adapter device to the WDM device stack. |
| [PcAddContentHandlers function](nf-portcls-pcaddcontenthandlers.md) | The PcAddContentHandlers function provides the system with a list of functions that handle protected content. |
| [PcAddStreamResource function](nf-portcls-pcaddstreamresource.md) | PcAddStreamResource adds a stream resource. |
| [PcCompleteIrp function](nf-portcls-pccompleteirp.md) | The PcCompleteIrp function completes an IRP that was previously marked as pending. |
| [PcCompletePendingPropertyRequest function](nf-portcls-pccompletependingpropertyrequest.md) | The PcCompletePendingPropertyRequest function is called to complete a pending property request. |
| [PcCreateContentMixed function](nf-portcls-pccreatecontentmixed.md) | The PcCreateContentMixed function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. |
| [PcDestroyContent function](nf-portcls-pcdestroycontent.md) | The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical. |
| [PcDispatchIrp function](nf-portcls-pcdispatchirp.md) | The PcDispatchIrp function dispatches an IRP to the PortCls system driver's default handler. |
| [PcForwardContentToDeviceObject function](nf-portcls-pcforwardcontenttodeviceobject.md) | The PcForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content. |
| [PcForwardContentToFileObject function](nf-portcls-pcforwardcontenttofileobject.md) | The PcForwardContentToFileObject function is obsolete and is maintained only to support existing drivers. |
| [PcForwardContentToInterface function](nf-portcls-pcforwardcontenttointerface.md) | The PcForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. |
| [PcForwardIrpSynchronous function](nf-portcls-pcforwardirpsynchronous.md) | The PcForwardIrpSynchronous function is used by IRP handlers to forward Plug and Play IRPs to the physical device object (PDO). |
| [PcGetContentRights function](nf-portcls-pcgetcontentrights.md) | The PcGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the DrmGetContentRights function, and its parameter definitions and return value are also identical. |
| [PcGetDeviceProperty function](nf-portcls-pcgetdeviceproperty.md) | The PcGetDeviceProperty function returns the requested device property from the registry. |
| [PcGetPhysicalDeviceObject function](nf-portcls-pcgetphysicaldeviceobject.md) | The PcGetPhysicalDeviceObject function enables audio miniport drivers to retrieve the underlying physical device object of the audio device. |
| [PcGetTimeInterval function](nf-portcls-pcgettimeinterval.md) | The PcGetTimeInterval function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units. |
| [PcInitializeAdapterDriver function](nf-portcls-pcinitializeadapterdriver.md) | The PcInitializeAdapterDriver function binds an adapter driver to the PortCls system driver. |
| [PcNewDmaChannel function](nf-portcls-pcnewdmachannel.md) | The PcNewDmaChannel function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments. |
| [PcNewInterruptSync function](nf-portcls-pcnewinterruptsync.md) | The PcNewInterruptSync function creates and initializes an interrupt-synchronization object. |
| [PcNewMiniport function](nf-portcls-pcnewminiport.md) | The PcNewMiniport function creates an instance of one of the system-supplied miniport drivers that are built into the PortCls system driver, portcls.sys. |
| [PcNewPort function](nf-portcls-pcnewport.md) | The PcNewPort function creates a new system-supplied port-driver object, whose interface (derived from base class IPort) is specified by a class ID. |
| [PcNewRegistryKey function](nf-portcls-pcnewregistrykey.md) | The PcNewRegistryKey function opens or creates a new registry key and creates an IRegistryKey object to represent the key. The caller accesses the key through this object. |
| [PcNewResourceList function](nf-portcls-pcnewresourcelist.md) | The PcNewResourceList function creates and initializes a resource list. |
| [PcNewResourceSublist function](nf-portcls-pcnewresourcesublist.md) | The PcNewResourceSublist function creates and initializes an empty resource list that is derived from another resource list. |
| [PcNewServiceGroup function](nf-portcls-pcnewservicegroup.md) | The PcNewServiceGroup function creates and initializes a service group. |
| [PcRegisterAdapterPnpManagement function](nf-portcls-pcregisteradapterpnpmanagement.md) | The PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver. It is used to support PnP rebalance. |
| [PcRegisterAdapterPowerManagement function](nf-portcls-pcregisteradapterpowermanagement.md) | The PcRegisterAdapterPowerManagement function registers the adapter's power-management interface with the PortCls system driver. |
| [PcRegisterIoTimeout function](nf-portcls-pcregisteriotimeout.md) | The PcRegisterIoTimeout function registers a driver-supplied I/O-timer callback routine for a specified device object. |
| [PcRegisterPhysicalConnection function](nf-portcls-pcregisterphysicalconnection.md) | The PcRegisterPhysicalConnection function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver. |
| [PcRegisterPhysicalConnectionFromExternal function](nf-portcls-pcregisterphysicalconnectionfromexternal.md) | The PcRegisterPhysicalConnectionFromExternal function registers a physical connection to an audio adapter filter from an external audio adapter filter. |
| [PcRegisterPhysicalConnectionToExternal function](nf-portcls-pcregisterphysicalconnectiontoexternal.md) | The PcRegisterPhysicalConnectionToExternal function registers a physical connection from an audio adapter filter to an external audio adapter filter. |
| [PcRegisterSubdevice function](nf-portcls-pcregistersubdevice.md) | The PcRegisterSubdevice function registers a subdevice to make it available for use by clients. |
| [PcRemoveStreamResource function](nf-portcls-pcremovestreamresource.md) | PcRemoveStreamResource removes an existing stream resource. |
| [PcRequestNewPowerState function](nf-portcls-pcrequestnewpowerstate.md) | The PcRequestNewPowerState function is used to request a new power state for the device. This function is typically not needed by adapter drivers but can occasionally be useful in working around some kinds of hardware problems. |
| [PcUnregisterAdapterPnpManagement function](nf-portcls-pcunregisteradapterpnpmanagement.md) | The PcUnregisterAdapterPnpManagement function unregisters the audio adapter's PnP management interface from the PortCls class driver. It is used to support PnP rebalance. |
| [PcUnregisterAdapterPowerManagement function](nf-portcls-pcunregisteradapterpowermanagement.md) | The PcUnregisterAdapterPowerManagement function unregisters the audio adapter's power management interface from the PortCls class driver. The PcUnregisterAdapterPowerManagement function is available in Windows 7 and later versions of Windows. |
| [PcUnregisterIoTimeout function](nf-portcls-pcunregisteriotimeout.md) | The PcUnregisterIoTimeout function unregisters a driver-supplied I/O-timer callback routine for a specified device object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PCPFNEVENT_HANDLER callback](nc-portcls-pcpfnevent_handler.md) | An EventHandler routine processes event requests. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [*PPCMETHOD_ITEM structure](ns-portcls-__unnamed_struct_0c93_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [*PPCMETHOD_ITEM structure](ns-portcls-__unnamed_struct_0cec_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [*PPCNODE_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0c93_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [*PPCNODE_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cec_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [*PPCPIN_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0c93_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [*PPCPIN_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cec_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [PCAUTOMATION_TABLE structure](ns-portcls-__unnamed_struct_0c93_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCAUTOMATION_TABLE structure](ns-portcls-__unnamed_struct_0cb6_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCAUTOMATION_TABLE structure](ns-portcls-__unnamed_struct_0cec_6.md) | The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events. |
| [PCEVENT_ITEM structure](ns-portcls-__unnamed_struct_0c93_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCEVENT_ITEM structure](ns-portcls-__unnamed_struct_0cb6_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCEVENT_ITEM structure](ns-portcls-__unnamed_struct_0cec_5.md) | The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node. |
| [PCFILTER_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0c93_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCFILTER_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cb6_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCFILTER_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cec_9.md) | The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties. |
| [PCMETHOD_ITEM structure](ns-portcls-__unnamed_struct_0cb6_4.md) | The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node. |
| [PCNODE_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cb6_8.md) | The PCNODE_DESCRIPTOR structure describes a node in the filter that a topology miniport driver implements. |
| [PCPIN_DESCRIPTOR structure](ns-portcls-__unnamed_struct_0cb6_7.md) | The PCPIN_DESCRIPTOR structure describes a pin factory. |
| [PCPROPERTY_ITEM structure](ns-portcls-__unnamed_struct_0c93_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [PCPROPERTY_ITEM structure](ns-portcls-__unnamed_struct_0cb6_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [PCPROPERTY_ITEM structure](ns-portcls-__unnamed_struct_0cec_3.md) | The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node. |
| [_PCEVENT_REQUEST structure](ns-portcls-_pcevent_request.md) | The PCEVENT_REQUEST structure specifies an event request. |
| [_PCMETHOD_REQUEST structure](ns-portcls-_pcmethod_request.md) | The PCMETHOD_REQUEST structure specifies a method request. |
| [_PCNOTIFICATION_BUFFER structure](ns-portcls-_pcnotification_buffer.md) | The notification buffer used by IPortClsNotifications. |
| [_PCPROPERTY_REQUEST structure](ns-portcls-_pcproperty_request.md) | The PCPROPERTY_REQUEST structure specifies a property request. |
| [_PCSTREAMRESOURCE_DESCRIPTOR structure](ns-portcls-_pcstreamresource_descriptor.md) | PCSTREAMRESOURCE_DESCRIPTOR defines the stream resource. Use PCSTREAMRESOURCE_DESCRIPTOR_INIT to correctly initialize this structure. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [EPcMiniportEngineEvent enumeration](ne-portcls-epcminiportengineevent.md) | This topic introduces the EPcMiniportEngineEvent enum, and describes the parameters that provide additional information when the miniport driver reports a glitching error. |
| [PC_REBALANCE_TYPE enumeration](ne-portcls-pc_rebalance_type.md) | The PC_REBALANCE_TYPE enum describes the type of support for rebalancing. |
| [_PC_EXIT_LATENCY enumeration](ne-portcls-_pc_exit_latency.md) | This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0). |
| [_PcStreamResourceType enumeration](ne-portcls-_pcstreamresourcetype.md) | This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming. |
| [eChannelTargetType enumeration](ne-portcls-echanneltargettype.md) | The eChannelTargetType enumeration defines constants that specify a type of node (target) in a given channel. |
| [eEngineFormatType enumeration](ne-portcls-eengineformattype.md) | The eEngineFormatType enumeration defines constants that specify the audio data type supported by the audio engine. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAdapterPnpManagement interface](nn-portcls-iadapterpnpmanagement.md) | IAdapterPnpManagement is an interface that adapters should implement and register if they want to receive PnP management messages. |
| [IAdapterPowerManagement interface](nn-portcls-iadapterpowermanagement.md) | The IAdapterPowerManagement interface is used to manage the power state of an audio adapter. |
| [IAdapterPowerManagement2 interface](nn-portcls-iadapterpowermanagement2.md) | The IAdapterPowerManagement2 interface inherits from IUnknown and it is used to manage the power state of an audio adapter. |
| [IAdapterPowerManagement3 interface](nn-portcls-iadapterpowermanagement3.md) | The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages. |
| [IDmaChannel interface](nn-portcls-idmachannel.md) | The IDmaChannel interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters. |
| [IDmaChannelSlave interface](nn-portcls-idmachannelslave.md) | The IDmaChannelSlave interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in Introduction to Adapter Objects). |
| [IDrmPort interface](nn-portcls-idrmport.md) | The IDrmPort interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management). |
| [IDrmPort2 interface](nn-portcls-idrmport2.md) | The IDrmPort2 interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management). |
| [IInterruptSync interface](nn-portcls-iinterruptsync.md) | The IInterruptSync interface represents an interrupt sync object that synchronizes the execution of a list of interrupt service routines (ISRs) with non-ISR routines. |
| [IMiniport interface](nn-portcls-iminiport.md) | The IMiniport interface is the generic miniport interface that all miniport objects support. IMiniport inherits from the IUnknown interface. |
| [IMiniportAudioEngineNode interface](nn-portcls-iminiportaudioenginenode.md) | This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle. |
| [IMiniportAudioSignalProcessing interface](nn-portcls-iminiportaudiosignalprocessing.md) | The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes. |
| [IMiniportMidi interface](nn-portcls-iminiportmidi.md) | The IMiniportMidi interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device. |
| [IMiniportMidiStream interface](nn-portcls-iminiportmidistream.md) | The IMiniportMidiStream interface represents the MIDI stream that flows through a pin on a MIDI filter. |
| [IMiniportPnpNotify interface](nn-portcls-iminiportpnpnotify.md) | IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices) to receive PnP state change notifications. |
| [IMiniportStreamAudioEngineNode interface](nn-portcls-iminiportstreamaudioenginenode.md) | This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle. |
| [IMiniportStreamAudioEngineNode2 interface](nn-portcls-iminiportstreamaudioenginenode2.md) | The IMiniportStreamAudioEngineNode2 interface allows an audio miniport driver to extend the capabilities of the IMiniportStreamAudioEngineNode interface. |
| [IMiniportTopology interface](nn-portcls-iminiporttopology.md) | The IMiniportTopology interface is the primary interface of a Topology miniport driver. |
| [IMiniportWaveCyclic interface](nn-portcls-iminiportwavecyclic.md) | The IMiniportWaveCyclic interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device. |
| [IMiniportWaveCyclicStream interface](nn-portcls-iminiportwavecyclicstream.md) | The IMiniportWaveCyclicStream interface represents the wave stream that flows through a pin on a WaveCyclic filter. |
| [IMiniportWavePci interface](nn-portcls-iminiportwavepci.md) | The IMiniportWavePci interface is the primary interface that is exposed by the miniport driver for a WavePci audio device. |
| [IMiniportWavePciStream interface](nn-portcls-iminiportwavepcistream.md) | The IMiniportWavePciStream interface represents the wave stream that flows through a pin on a WavePci filter. |
| [IMiniportWaveRT interface](nn-portcls-iminiportwavert.md) | The IMiniportWaveRT interface is the primary interface that is exposed by the miniport driver for a WaveRT audio device. |
| [IMiniportWaveRTInputStream interface](nn-portcls-iminiportwavertinputstream.md) | The IMiniportWaveRTInputStream interface represents the input wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. IMiniportWaveRTInputStream inherits from the IUnknown interface. |
| [IMiniportWaveRTOutputStream interface](nn-portcls-iminiportwavertoutputstream.md) | The IMiniportWaveRTOutputStream interface represents the output wave stream. IMiniportWaveRTOutputStream inherits from the IUnknown interface. |
| [IMiniportWaveRTStream interface](nn-portcls-iminiportwavertstream.md) | The IMiniportWaveRTStream interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. |
| [IMiniportWaveRTStreamNotification interface](nn-portcls-iminiportwavertstreamnotification.md) | The IMiniportWaveRTStreamNotification interface is supported in Windows Vista and later Windows operating systems, and it augments the IMiniportWaveRTStream interface, providing additional methods to facilitate DMA driver event notifications. |
| [IMusicTechnology interface](nn-portcls-imusictechnology.md) | The IMusicTechnology interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver. |
| [IPinCount interface](nn-portcls-ipincount.md) | The IPinCount interface provides a means for the miniport driver to monitor and manipulate its pin counts dynamically as pins are instantiated and closed. |
| [IPinName interface](nn-portcls-ipinname.md) | In Windows 7 and later operating systems, the IPinName interface is used by miniport drivers to report and update the names of audio endpoints. |
| [IPort interface](nn-portcls-iport.md) | The IPort interface is the generic interface for audio port drivers. All audio port drivers expose IPort as part of their lower edge. The adapter driver calls the initialization method on this interface. IPort inherits from the IUnknown interface. |
| [IPortClsEtwHelper interface](nn-portcls-iportclsetwhelper.md) | The IPortClsEtwHelper interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions. |
| [IPortClsNotifications interface](nn-portcls-iportclsnotifications.md) | An interface implemented by ports to provide notification helpers to miniports to support audio module communication. |
| [IPortClsPnp interface](nn-portcls-iportclspnp.md) | IPortClsPnp is the PnP management interface that the port class driver (PortCls) exposes to the adapter. |
| [IPortClsPower interface](nn-portcls-iportclspower.md) | The IPortClsPower interface is supported in Windows Vista and later versions of Windows. IPortClsPower is the power management interface that the port class driver (PortCls) exposes to the adapter. |
| [IPortClsRuntimePower interface](nn-portcls-iportclsruntimepower.md) | IPortClsRuntimePower is the interface that the port class driver (PortCls) uses for accessing the runtime power management capabilities of the audio adapter. |
| [IPortClsStreamResourceManager interface](nn-portcls-iportclsstreamresourcemanager.md) | IPortClsStreamResourceManager is used to manage the registration of audio stream resources. |
| [IPortClsStreamResourceManager2 interface](nn-portcls-iportclsstreamresourcemanager2.md) | IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources. |
| [IPortClsVersion interface](nn-portcls-iportclsversion.md) | The IPortClsVersion interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver. |
| [IPortEvents interface](nn-portcls-iportevents.md) | The IPortEvents interface is used by miniport drivers to notify clients of hardware events. |
| [IPortMidi interface](nn-portcls-iportmidi.md) | The IPortMidi interface is the MIDI port driver's primary interface. |
| [IPortTopology interface](nn-portcls-iporttopology.md) | The IPortTopology interface provides generic port driver support to a topology miniport driver. |
| [IPortWMIRegistration interface](nn-portcls-iportwmiregistration.md) | The IPortWMIRegistration interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver. |
| [IPortWaveCyclic interface](nn-portcls-iportwavecyclic.md) | The IPortWaveCyclic interface is the WaveCyclic port driver's primary interface. |
| [IPortWavePci interface](nn-portcls-iportwavepci.md) | The IPortWavePci interface is the WavePci port driver's primary interface. |
| [IPortWavePciStream interface](nn-portcls-iportwavepcistream.md) | The IPortWavePciStream interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects. |
| [IPortWaveRT interface](nn-portcls-iportwavert.md) | The IPortWaveRT interface is supported in Windows Vista and later operating systems and it is the main interface that the WaveRT port driver exposes to the adapter driver that implements the WaveRT miniport driver object. |
| [IPortWaveRTStream interface](nn-portcls-iportwavertstream.md) | The IPortWaveRTStream interface is supported in Windows Vista and later operating systems, and it is a stream-specific interface that provides helper methods for use by the WaveRT miniport driver. |
| [IPowerNotify interface](nn-portcls-ipowernotify.md) | The IPowerNotify interface is an optional interface that miniport drivers can expose if they require advance notification of impending power-state changes. |
| [IPreFetchOffset interface](nn-portcls-iprefetchoffset.md) | The IPreFetchOffset interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream. |
| [IRegistryKey interface](nn-portcls-iregistrykey.md) | The IRegistryKey interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys. |
| [IResourceList interface](nn-portcls-iresourcelist.md) | The IResourceList interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time. |
| [IServiceGroup interface](nn-portcls-iservicegroup.md) | The IServiceGroup interface encapsulates a group of objects that all require notification of the same service request. |
| [IServiceSink interface](nn-portcls-iservicesink.md) | The IServiceSink interface encapsulates handling of a service request. |
| [IUnregisterPhysicalConnection interface](nn-portcls-iunregisterphysicalconnection.md) | The IUnregisterPhysicalConnection interface implements three methods to remove a registered physical connection. |
| [IUnregisterSubdevice interface](nn-portcls-iunregistersubdevice.md) | The IUnregisterSubdevice interface implements a method to remove a registered subdevice. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IAdapterPowerManagement2::PowerChangeState2 method](nf-portcls-iadapterpowermanagement2-powerchangestate2.md) | Portcls calls the IAdapterPowerManagement2 |
| [IAdapterPowerManagement3::D3ExitLatencyChanged method](nf-portcls-iadapterpowermanagement3-d3exitlatencychanged.md) | PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value. |
| [IAdapterPowerManagement::PowerChangeState method](nf-portcls-iadapterpowermanagement-powerchangestate.md) | The PowerChangeState method requests that the device change to a new power state. |
| [IAdapterPowerManagement::QueryDeviceCapabilities method](nf-portcls-iadapterpowermanagement-querydevicecapabilities.md) | The QueryDeviceCapabilities method is called by PortCls in response to a Plug and Play IRP_MN_QUERY_CAPABILITIES IRP. |
| [IAdapterPowerManagement::QueryPowerChangeState method](nf-portcls-iadapterpowermanagement-querypowerchangestate.md) | The QueryPowerChangeState method is called by PortCls in response to the receipt of an IRP_MN_QUERY_POWER power IRP. |
| [IDrmPort2::AddContentHandlers method](nf-portcls-idrmport2-addcontenthandlers.md) | The AddContentHandlers method provides the system with a list of functions that handle protected content. |
| [IDrmPort2::ForwardContentToDeviceObject method](nf-portcls-idrmport2-forwardcontenttodeviceobject.md) | The ForwardContentToDeviceObject method accepts a device object representing a device to which the caller intends to forward protected content. |
| [IInterruptSync::CallSynchronizedRoutine method](nf-portcls-iinterruptsync-callsynchronizedroutine.md) | The CallSynchronizedRoutine method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs. |
| [IInterruptSync::Connect method](nf-portcls-iinterruptsync-connect.md) | The Connect method connects the synchronization object to the interrupt. |
| [IInterruptSync::Disconnect method](nf-portcls-iinterruptsync-disconnect.md) | The Disconnect method disconnects the synchronization object from the interrupt. |
| [IInterruptSync::GetKInterrupt method](nf-portcls-iinterruptsync-getkinterrupt.md) | The GetKInterrupt method gets a WDM interrupt object from a port-class synchronization object. |
| [IInterruptSync::RegisterServiceRoutine method](nf-portcls-iinterruptsync-registerserviceroutine.md) | The RegisterServiceRoutine method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs. |
| [IMiniportAudioEngineNode::GetAudioEngineDescriptor method](nf-portcls-iminiportaudioenginenode-getaudioenginedescriptor.md) | Gets the descriptor for the audio engine node. |
| [IMiniportAudioEngineNode::GetBufferSizeRange method](nf-portcls-iminiportaudioenginenode-getbuffersizerange.md) | Gets the minimum and maximum buffer size that the hardware audio engine can support. |
| [IMiniportAudioEngineNode::GetDeviceAttributeSteppings method](nf-portcls-iminiportaudioenginenode-getdeviceattributesteppings.md) | Gets the allowed stepping value for the audio device attribute. |
| [IMiniportAudioEngineNode::GetDeviceChannelCount method](nf-portcls-iminiportaudioenginenode-getdevicechannelcount.md) | Gets a count of the number of channels supported by the audio device. |
| [IMiniportAudioEngineNode::GetDeviceChannelMute method](nf-portcls-iminiportaudioenginenode-getdevicechannelmute.md) | Gets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelPeakMeter method](nf-portcls-iminiportaudioenginenode-getdevicechannelpeakmeter.md) | Gets the PeakMeter value for the audio device channel. |
| [IMiniportAudioEngineNode::GetDeviceChannelVolume method](nf-portcls-iminiportaudioenginenode-getdevicechannelvolume.md) | Gets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::GetDeviceFormat method](nf-portcls-iminiportaudioenginenode-getdeviceformat.md) | Gets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::GetEngineFormatSize method](nf-portcls-iminiportaudioenginenode-getengineformatsize.md) | Gets the format type and the buffer size for the audio engine's audio data format. |
| [IMiniportAudioEngineNode::GetGfxState method](nf-portcls-iminiportaudioenginenode-getgfxstate.md) | Gets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioEngineNode::GetMixFormat method](nf-portcls-iminiportaudioenginenode-getmixformat.md) | Gets the audio data format for the audio engine mixer. |
| [IMiniportAudioEngineNode::GetSupportedDeviceFormats method](nf-portcls-iminiportaudioenginenode-getsupporteddeviceformats.md) | Gets the supported audio data formats for the audio device. |
| [IMiniportAudioEngineNode::SetDeviceChannelMute method](nf-portcls-iminiportaudioenginenode-setdevicechannelmute.md) | Sets the state of the Mute node for the audio device channel. |
| [IMiniportAudioEngineNode::SetDeviceChannelVolume method](nf-portcls-iminiportaudioenginenode-setdevicechannelvolume.md) | Sets the volume level for a given channel of the audio device. |
| [IMiniportAudioEngineNode::SetDeviceFormat method](nf-portcls-iminiportaudioenginenode-setdeviceformat.md) | Sets the audio data format for an audio device. |
| [IMiniportAudioEngineNode::SetGfxState method](nf-portcls-iminiportaudioenginenode-setgfxstate.md) | Sets the state of the global effects (GFX) node in the audio engine. |
| [IMiniportAudioSignalProcessing::GetModes method](nf-portcls-iminiportaudiosignalprocessing-getmodes.md) | The GetModes method, Gets the audio signal processing modes supported by an audio pin. |
| [IMiniportMidi::Init method](nf-portcls-iminiportmidi-init.md) | The Init method initializes the MIDI miniport object. |
| [IMiniportMidi::NewStream method](nf-portcls-iminiportmidi-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportMidi::Service method](nf-portcls-iminiportmidi-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportMidiStream::Read method](nf-portcls-iminiportmidistream-read.md) | The Read method reads data from an incoming MIDI stream. |
| [IMiniportMidiStream::SetFormat method](nf-portcls-iminiportmidistream-setformat.md) | The SetFormat method sets the KS data format of the MIDI stream. |
| [IMiniportMidiStream::SetState method](nf-portcls-iminiportmidistream-setstate.md) | The SetState method sets the stream's transport state to a new state value. |
| [IMiniportMidiStream::Write method](nf-portcls-iminiportmidistream-write.md) | The Write method writes data to an outgoing MIDI stream. |
| [IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer method](nf-portcls-iminiportstreamaudioenginenode2-setstreamcurrentwritepositionforlastbuffer.md) | Sets the current cursor position in the last audio data stream that was written to the audio buffer. |
| [IMiniportStreamAudioEngineNode::GetLfxState method](nf-portcls-iminiportstreamaudioenginenode-getlfxstate.md) | Gets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings method](nf-portcls-iminiportstreamaudioenginenode-getstreamattributesteppings.md) | Gets the allowed stepping value for the audio stream attribute. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelCount method](nf-portcls-iminiportstreamaudioenginenode-getstreamchannelcount.md) | Gets a count of the number of channels available for the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelMute method](nf-portcls-iminiportstreamaudioenginenode-getstreamchannelmute.md) | Gets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelPeakMeter method](nf-portcls-iminiportstreamaudioenginenode-getstreamchannelpeakmeter.md) | Gets the value of the PeakMeter node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamChannelVolume method](nf-portcls-iminiportstreamaudioenginenode-getstreamchannelvolume.md) | Gets the current volume level that is applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::GetStreamLinearBufferPosition method](nf-portcls-iminiportstreamaudioenginenode-getstreamlinearbufferposition.md) | Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream. |
| [IMiniportStreamAudioEngineNode::GetStreamPresentationPosition method](nf-portcls-iminiportstreamaudioenginenode-getstreampresentationposition.md) | Gets the current cursor position in the audio data stream that is being rendered to the endpoint. |
| [IMiniportStreamAudioEngineNode::SetLfxState method](nf-portcls-iminiportstreamaudioenginenode-setlfxstate.md) | Sets the state of the local effects (LFX) node that is in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelMute method](nf-portcls-iminiportstreamaudioenginenode-setstreamchannelmute.md) | Sets the state of the Mute node in the path of the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamChannelVolume method](nf-portcls-iminiportstreamaudioenginenode-setstreamchannelvolume.md) | Sets the volume level to be applied to the audio stream. |
| [IMiniportStreamAudioEngineNode::SetStreamCurrentWritePosition method](nf-portcls-iminiportstreamaudioenginenode-setstreamcurrentwriteposition.md) | Sets the current cursor position in the audio data stream that is being captured from the endpoint. |
| [IMiniportStreamAudioEngineNode::SetStreamLoopbackProtection method](nf-portcls-iminiportstreamaudioenginenode-setstreamloopbackprotection.md) | Sets the loopback protection status of the audio engine node. |
| [IMiniportTopology::Init method](nf-portcls-iminiporttopology-init.md) | The Init method initializes the topology miniport object. |
| [IMiniportWaveCyclic::Init method](nf-portcls-iminiportwavecyclic-init.md) | The Init method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWaveCyclic::NewStream method](nf-portcls-iminiportwavecyclic-newstream.md) | The NewStream method creates a new instance of a logical stream that is associated with a specified physical channel. |
| [IMiniportWaveCyclicStream::GetPosition method](nf-portcls-iminiportwavecyclicstream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWaveCyclicStream::NormalizePhysicalPosition method](nf-portcls-iminiportwavecyclicstream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWaveCyclicStream::SetFormat method](nf-portcls-iminiportwavecyclicstream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWaveCyclicStream::SetNotificationFreq method](nf-portcls-iminiportwavecyclicstream-setnotificationfreq.md) | The SetNotificationFreq method controls the frequency at which notification interrupts are generated by setting the interval between successive interrupts. |
| [IMiniportWaveCyclicStream::SetState method](nf-portcls-iminiportwavecyclicstream-setstate.md) | The SetState method sets the new state of playback or recording for the stream. |
| [IMiniportWaveCyclicStream::Silence method](nf-portcls-iminiportwavecyclicstream-silence.md) | The Silence method is used to copy silence samples to a specified buffer. |
| [IMiniportWavePci::Init method](nf-portcls-iminiportwavepci-init.md) | The Init method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list. |
| [IMiniportWavePci::NewStream method](nf-portcls-iminiportwavepci-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportWavePci::Service method](nf-portcls-iminiportwavepci-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::GetAllocatorFraming method](nf-portcls-iminiportwavepcistream-getallocatorframing.md) | The GetAllocatorFraming method gets the preferred allocator-framing parameters for the stream. |
| [IMiniportWavePciStream::GetPosition method](nf-portcls-iminiportwavepcistream-getposition.md) | The GetPosition method gets the current position of the stream. |
| [IMiniportWavePciStream::MappingAvailable method](nf-portcls-iminiportwavepcistream-mappingavailable.md) | The MappingAvailable method indicates that a new mapping is available. |
| [IMiniportWavePciStream::NormalizePhysicalPosition method](nf-portcls-iminiportwavepcistream-normalizephysicalposition.md) | The NormalizePhysicalPosition method converts a physical buffer position to a time-based value. |
| [IMiniportWavePciStream::RevokeMappings method](nf-portcls-iminiportwavepcistream-revokemappings.md) | The RevokeMappings method revokes mappings that were previously obtained through IPortWavePciStream |
| [IMiniportWavePciStream::Service method](nf-portcls-iminiportwavepcistream-service.md) | The Service method notifies the miniport driver of a request for service. |
| [IMiniportWavePciStream::SetFormat method](nf-portcls-iminiportwavepcistream-setformat.md) | The SetFormat method sets the KS data format of the wave stream. |
| [IMiniportWavePciStream::SetState method](nf-portcls-iminiportwavepcistream-setstate.md) | The SetState method changes the state of the stream transport. |
| [IMiniportWaveRT::GetDeviceDescription method](nf-portcls-iminiportwavert-getdevicedescription.md) | The GetDeviceDescription method returns a pointer to a DEVICE_DESCRIPTION structure describing the device. |
| [IMiniportWaveRT::Init method](nf-portcls-iminiportwavert-init.md) | The Init method initializes the WaveRT miniport driver object. |
| [IMiniportWaveRT::NewStream method](nf-portcls-iminiportwavert-newstream.md) | The NewStream method creates a new instance of a WaveRT stream object. |
| [IMiniportWaveRTInputStream::GetReadPacket method](nf-portcls-iminiportwavertinputstream-getreadpacket.md) | Returns information about captured data. |
| [IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition method](nf-portcls-iminiportwavertoutputstream-getoutputstreampresentationposition.md) | Returns stream presentation information. |
| [IMiniportWaveRTOutputStream::GetPacketCount method](nf-portcls-iminiportwavertoutputstream-getpacketcount.md) | GetPacketCount returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware. |
| [IMiniportWaveRTOutputStream::SetWritePacket method](nf-portcls-iminiportwavertoutputstream-setwritepacket.md) | SetWritePacket informs the driver that the OS has written valid data to the WaveRT buffer. |
| [IMiniportWaveRTStreamNotification::AllocateBufferWithNotification method](nf-portcls-iminiportwavertstreamnotification-allocatebufferwithnotification.md) | The AllocateAudioBufferWithNotification method allocates a cyclic buffer for audio data when you want to implement DMA-driven event notification. If you do not want event notification, you must use IMiniportWaveRTStream |
| [IMiniportWaveRTStreamNotification::FreeBufferWithNotification method](nf-portcls-iminiportwavertstreamnotification-freebufferwithnotification.md) | The FreeBufferWithNotification method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStreamNotification |
| [IMiniportWaveRTStreamNotification::RegisterNotificationEvent method](nf-portcls-iminiportwavertstreamnotification-registernotificationevent.md) | The RegisterNotificationEvent method registers an event to be notified for DMA-driven event notification. |
| [IMiniportWaveRTStreamNotification::UnregisterNotificationEvent method](nf-portcls-iminiportwavertstreamnotification-unregisternotificationevent.md) | The UnregisterNotificationEvent method unregisters an event from DMA driven event notification. |
| [IMusicTechnology::SetTechnology method](nf-portcls-imusictechnology-settechnology.md) | The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins. |
| [IPinCount::PinCount method](nf-portcls-ipincount-pincount.md) | The PinCount method queries the miniport driver for its pin count. |
| [IPinName::GetPinName method](nf-portcls-ipinname-getpinname.md) | The GetPinName method retrieves the friendly name of an audio endpoint. |
| [IPortClsEtwHelper::MiniportWriteEtwEvent method](nf-portcls-iportclsetwhelper-miniportwriteetwevent.md) | The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event. |
| [IPortClsNotifications::AllocNotificationBuffer method](nf-portcls-iportclsnotifications-allocnotificationbuffer.md) | Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::FreeNotificationBuffer method](nf-portcls-iportclsnotifications-freenotificationbuffer.md) | Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. |
| [IPortClsNotifications::SendNotification method](nf-portcls-iportclsnotifications-sendnotification.md) | Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps. |
| [IPortClsPnp::RegisterAdapterPnpManagement method](nf-portcls-iportclspnp-registeradapterpnpmanagement.md) | The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls. |
| [IPortClsPnp::UnregisterAdapterPnpManagement method](nf-portcls-iportclspnp-unregisteradapterpnpmanagement.md) | The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls. |
| [IPortClsPower::RegisterAdapterPowerManagement method](nf-portcls-iportclspower-registeradapterpowermanagement.md) | The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls. |
| [IPortClsPower::SetIdlePowerManagement method](nf-portcls-iportclspower-setidlepowermanagement.md) | The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection. |
| [IPortClsPower::UnregisterAdapterPowerManagement method](nf-portcls-iportclspower-unregisteradapterpowermanagement.md) | The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls. |
| [IPortClsRuntimePower::RegisterPowerControlCallback method](nf-portcls-iportclsruntimepower-registerpowercontrolcallback.md) | The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback. |
| [IPortClsRuntimePower::SendPowerControl method](nf-portcls-iportclsruntimepower-sendpowercontrol.md) | The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter. |
| [IPortClsRuntimePower::UnregisterPowerControlCallback method](nf-portcls-iportclsruntimepower-unregisterpowercontrolcallback.md) | The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback. |
| [IPortClsStreamResourceManager2::AddStreamResource2 method](nf-portcls-iportclsstreamresourcemanager2-addstreamresource2.md) | AddStreamResource2 adds a stream resource. Two type of stream resources are supported |
| [IPortClsVersion::GetVersion method](nf-portcls-iportclsversion-getversion.md) | The GetVersion method returns the version of the Windows operating system that the driver is running on. |
| [IPortEvents::AddEventToEventList method](nf-portcls-iportevents-addeventtoeventlist.md) | The AddEventToEventList method adds an event to the port driver's event list. |
| [IPortEvents::GenerateEventList method](nf-portcls-iportevents-generateeventlist.md) | The GenerateEventList method notifies clients through the port driver's list of event entries that a particular event has occurred. |
| [IPortMidi::Notify method](nf-portcls-iportmidi-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortMidi::RegisterServiceGroup method](nf-portcls-iportmidi-registerservicegroup.md) | The RegisterServiceGroup method registers the service group to be used for the IPortMidi |
| [IPortWMIRegistration::RegisterWMIProvider method](nf-portcls-iportwmiregistration-registerwmiprovider.md) | The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls. |
| [IPortWMIRegistration::UnregisterWMIProvider method](nf-portcls-iportwmiregistration-unregisterwmiprovider.md) | The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls. |
| [IPortWaveCyclic::NewMasterDmaChannel method](nf-portcls-iportwavecyclic-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWaveCyclic::NewSlaveDmaChannel method](nf-portcls-iportwavecyclic-newslavedmachannel.md) | The NewSlaveDmaChannel method creates a new instance of a subordinate DMA channel. |
| [IPortWaveCyclic::Notify method](nf-portcls-iportwavecyclic-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [IPortWavePci::NewMasterDmaChannel method](nf-portcls-iportwavepci-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [IPortWavePci::Notify method](nf-portcls-iportwavepci-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. |
| [IPortWavePciStream::GetMapping method](nf-portcls-iportwavepcistream-getmapping.md) | The GetMapping method obtains a mapping from the port driver and associates a tag with the mapping. |
| [IPortWavePciStream::ReleaseMapping method](nf-portcls-iportwavepcistream-releasemapping.md) | The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream |
| [IPortWavePciStream::TerminatePacket method](nf-portcls-iportwavepcistream-terminatepacket.md) | The TerminatePacket method terminates the packet currently being mapped. |
| [IPortWaveRTStream::AllocateContiguousPagesForMdl method](nf-portcls-iportwavertstream-allocatecontiguouspagesformdl.md) | The AllocateContiguousPagesForMdl method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::AllocatePagesForMdl method](nf-portcls-iportwavertstream-allocatepagesformdl.md) | The AllocatePagesForMdl method allocates a list of nonpaged physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them. |
| [IPortWaveRTStream::FreePagesFromMdl method](nf-portcls-iportwavertstream-freepagesfrommdl.md) | The FreePagesFromMdl method frees a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPageAddress method](nf-portcls-iportwavertstream-getphysicalpageaddress.md) | The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL). |
| [IPortWaveRTStream::GetPhysicalPagesCount method](nf-portcls-iportwavertstream-getphysicalpagescount.md) | The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL). |
| [IPortWaveRTStream::MapAllocatedPages method](nf-portcls-iportwavertstream-mapallocatedpages.md) | The MapAllocatedPages method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode. |
| [IPortWaveRTStream::UnmapAllocatedPages method](nf-portcls-iportwavertstream-unmapallocatedpages.md) | The UnmapAllocatedPages method releases a mapping. |
| [IPowerNotify::PowerChangeNotify method](nf-portcls-ipowernotify-powerchangenotify.md) | The PowerChangeNotify method notifies the miniport driver of changes in the power state. |
| [IPreFetchOffset::SetPreFetchOffset method](nf-portcls-iprefetchoffset-setprefetchoffset.md) | The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream. |
| [IRegistryKey::DeleteKey method](nf-portcls-iregistrykey-deletekey.md) | The DeleteKey method deletes the registry key. |
| [IRegistryKey::EnumerateKey method](nf-portcls-iregistrykey-enumeratekey.md) | The EnumerateKey method returns information about the subkeys of the open key. |
| [IRegistryKey::EnumerateValueKey method](nf-portcls-iregistrykey-enumeratevaluekey.md) | The EnumerateValueKey method returns information about a registry entry that contains a value key. |
| [IRegistryKey::NewSubKey method](nf-portcls-iregistrykey-newsubkey.md) | The NewSubKey method either creates a new registry subkey or opens an existing subkey under the key represented by the IRegistryKey object. |
| [IRegistryKey::QueryKey method](nf-portcls-iregistrykey-querykey.md) | The QueryKey method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes. |
| [IRegistryKey::QueryRegistryValues method](nf-portcls-iregistrykey-queryregistryvalues.md) | The QueryRegistryValues method allows the caller to query several values from the registry with a single call. |
| [IRegistryKey::QueryValueKey method](nf-portcls-iregistrykey-queryvaluekey.md) | The QueryValueKey method retrieves information about a registry key's value entries, including their names, types, data sizes, and values. |
| [IRegistryKey::SetValueKey method](nf-portcls-iregistrykey-setvaluekey.md) | The SetValueKey method replaces or creates a value entry under the open key. |
| [IResourceList::AddEntry method](nf-portcls-iresourcelist-addentry.md) | The AddEntry method adds an entry to a resource list. |
| [IResourceList::AddEntryFromParent method](nf-portcls-iresourcelist-addentryfromparent.md) | The AddEntryFromParent method adds to a resource list an entry found in the resource list's parent list. |
| [IResourceList::FindTranslatedEntry method](nf-portcls-iresourcelist-findtranslatedentry.md) | The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found. |
| [IResourceList::FindUntranslatedEntry method](nf-portcls-iresourcelist-finduntranslatedentry.md) | The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found. |
| [IResourceList::NumberOfEntries method](nf-portcls-iresourcelist-numberofentries.md) | The NumberOfEntries method returns the number of resource items in the resource list. |
| [IResourceList::NumberOfEntriesOfType method](nf-portcls-iresourcelist-numberofentriesoftype.md) | The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described. |
| [IResourceList::TranslatedList method](nf-portcls-iresourcelist-translatedlist.md) | The TranslatedList method returns the list of translated resources. |
| [IResourceList::UntranslatedList method](nf-portcls-iresourcelist-untranslatedlist.md) | The UntranslatedList method returns the list of untranslated resources. |
| [IServiceGroup::AddMember method](nf-portcls-iservicegroup-addmember.md) | The AddMember method adds a member to the service group. |
| [IServiceGroup::CancelDelayedService method](nf-portcls-iservicegroup-canceldelayedservice.md) | The CancelDelayedService method cancels the previously requested delayed service. |
| [IServiceGroup::RemoveMember method](nf-portcls-iservicegroup-removemember.md) | The RemoveMember method removes the specified member from the service group. |
| [IServiceGroup::RequestDelayedService method](nf-portcls-iservicegroup-requestdelayedservice.md) | The RequestDelayedService method requests service after the specified delay. |
| [IServiceGroup::RequestService method](nf-portcls-iservicegroup-requestservice.md) | TBD |
| [IServiceGroup::SupportDelayedService method](nf-portcls-iservicegroup-supportdelayedservice.md) | The SupportDelayedService method indicates that the service group should prepare to support delayed service. |
| [IServiceSink::RequestService method](nf-portcls-iservicesink-requestservice.md) | The RequestService method is called to forward a service request to an IServiceSink object. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnection method](nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnection.md) | The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method](nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectionfromexternal.md) | The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal. |
| [IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal method](nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectiontoexternal.md) | The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal. |
| [IUnregisterSubdevice::UnregisterSubdevice method](nf-portcls-iunregistersubdevice-unregistersubdevice.md) | The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice. |
