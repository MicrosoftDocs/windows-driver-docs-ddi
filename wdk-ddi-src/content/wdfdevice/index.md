---
UID: NA:wdfdevice
ms.assetid: 24b2e402-56ef-3f36-b4f0-426a9d758500
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfdevice.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfdevice.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function](nf-wdfdevice-wdf_device_interface_property_data_init.md) | The WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_INTERFACE_PROPERTY_DATA structure. |
| [WDF_DEVICE_PNP_CAPABILITIES_INIT function](nf-wdfdevice-wdf_device_pnp_capabilities_init.md) | The WDF_DEVICE_PNP_CAPABILITIES_INIT function initializes a WDF_DEVICE_PNP_CAPABILITIES structure. |
| [WDF_DEVICE_POWER_CAPABILITIES_INIT function](nf-wdfdevice-wdf_device_power_capabilities_init.md) | The WDF_DEVICE_POWER_CAPABILITIES_INIT function initializes a WDF_DEVICE_POWER_CAPABILITIES structure. |
| [WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function](nf-wdfdevice-wdf_device_power_policy_idle_settings_init.md) | The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure. |
| [WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function](nf-wdfdevice-wdf_device_power_policy_wake_settings_init.md) | The WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure. |
| [WDF_DEVICE_PROPERTY_DATA_INIT function](nf-wdfdevice-wdf_device_property_data_init.md) | The WDF_DEVICE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_PROPERTY_DATA structure. |
| [WDF_DEVICE_STATE_INIT function](nf-wdfdevice-wdf_device_state_init.md) | The WDF_DEVICE_STATE_INIT function initializes a driver's WDF_DEVICE_STATE structure. |
| [WDF_FILEOBJECT_CONFIG_INIT function](nf-wdfdevice-wdf_fileobject_config_init.md) | The WDF_FILEOBJECT_CONFIG_INIT function initializes a driver's WDF_FILEOBJECT_CONFIG structure. |
| [WDF_IO_TYPE_CONFIG_INIT function](nf-wdfdevice-wdf_io_type_config_init.md) | The WDF_IO_TYPE_CONFIG_INIT function initializes a driver's WDF_IO_TYPE_CONFIG structure. |
| [WDF_PNPPOWER_EVENT_CALLBACKS_INIT function](nf-wdfdevice-wdf_pnppower_event_callbacks_init.md) | The WDF_PNPPOWER_EVENT_CALLBACKS_INIT function initializes a driver's WDF_PNPPOWER_EVENT_CALLBACKS structure. |
| [WDF_POWER_FRAMEWORK_SETTINGS_INIT function](nf-wdfdevice-wdf_power_framework_settings_init.md) | The WDF_POWER_FRAMEWORK_SETTINGS_INIT function initializes a WDF_POWER_FRAMEWORK_SETTINGS structure. |
| [WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function](nf-wdfdevice-wdf_power_policy_event_callbacks_init.md) | The WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function initializes a driver's WDF_POWER_POLICY_EVENT_CALLBACKS structure. |
| [WDF_REMOVE_LOCK_OPTIONS_INIT function](nf-wdfdevice-wdf_remove_lock_options_init.md) | The WDF_REMOVE_LOCK_OPTIONS_INIT function initializes a WDF_REMOVE_LOCK_OPTIONS structure. |
| [WdfDevStateIsNP function](nf-wdfdevice-wdfdevstateisnp.md) | The WdfDevStateIsNP method returns a Boolean value that indicates whether a specified power state or power policy state is a nonpageable state. |
| [WdfDevStateNormalize function](nf-wdfdevice-wdfdevstatenormalize.md) | The WdfDevStateNormalize method removes extra bits from a specified framework state machine value so that the driver can use the value as an index into an array of machine states. |
| [WdfDeviceAddDependentUsageDeviceObject function](nf-wdfdevice-wdfdeviceadddependentusagedeviceobject.md) | The WdfDeviceAddDependentUsageDeviceObject method indicates that a specified device depends on another device when the specified device is used to store special files. |
| [WdfDeviceAddRemovalRelationsPhysicalDevice function](nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice.md) | The WdfDeviceAddRemovalRelationsPhysicalDevice method indicates that a specified device must be removed when another specified device is removed. |
| [WdfDeviceAllocAndQueryInterfaceProperty function](nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md) | The WdfDeviceAllocAndQueryInterfaceProperty method allocates a buffer and retrieves a specified device interface property. |
| [WdfDeviceAllocAndQueryProperty function](nf-wdfdevice-wdfdeviceallocandqueryproperty.md) | The WdfDeviceAllocAndQueryProperty method allocates a buffer and retrieves a specified device property. |
| [WdfDeviceAllocAndQueryPropertyEx function](nf-wdfdevice-wdfdeviceallocandquerypropertyex.md) | The WdfDeviceAllocAndQueryPropertyEx method allocates a buffer and retrieves a specified device property. |
| [WdfDeviceAssignInterfaceProperty function](nf-wdfdevice-wdfdeviceassigninterfaceproperty.md) | The WdfDeviceAssignInterfaceProperty method modifies the current value of a device interface property. |
| [WdfDeviceAssignMofResourceName function](nf-wdfdevice-wdfdeviceassignmofresourcename.md) | The WdfDeviceAssignMofResourceName method registers a MOF resource name for a specified device. |
| [WdfDeviceAssignProperty function](nf-wdfdevice-wdfdeviceassignproperty.md) | The WdfDeviceAssignProperty method modifies the current setting of a device property. |
| [WdfDeviceAssignS0IdleSettings function](nf-wdfdevice-wdfdeviceassigns0idlesettings.md) | The WdfDeviceAssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state. |
| [WdfDeviceAssignSxWakeSettings function](nf-wdfdevice-wdfdeviceassignsxwakesettings.md) | The WdfDeviceAssignSxWakeSettings method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state. |
| [WdfDeviceClearRemovalRelationsDevices function](nf-wdfdevice-wdfdeviceclearremovalrelationsdevices.md) | The WdfDeviceClearRemovalRelationsDevices method removes all devices from the list of devices that must be removed when a specified device is removed. |
| [WdfDeviceConfigureRequestDispatching function](nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md) | The WdfDeviceConfigureRequestDispatching method causes the framework to queue a specified type of I/O requests to a specified I/O queue. |
| [WdfDeviceConfigureWdmIrpDispatchCallback function](nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md) | The WdfDeviceConfigureWdmIrpDispatchCallback method registers a driver's EvtDeviceWdmIrpDispatch callback function. |
| [WdfDeviceCreate function](nf-wdfdevice-wdfdevicecreate.md) | The WdfDeviceCreate method creates a framework device object. |
| [WdfDeviceCreateDeviceInterface function](nf-wdfdevice-wdfdevicecreatedeviceinterface.md) | The WdfDeviceCreateDeviceInterface method creates a device interface for a specified device. |
| [WdfDeviceCreateSymbolicLink function](nf-wdfdevice-wdfdevicecreatesymboliclink.md) | The WdfDeviceCreateSymbolicLink method creates a symbolic link to a specified device. |
| [WdfDeviceEnqueueRequest function](nf-wdfdevice-wdfdeviceenqueuerequest.md) | The WdfDeviceEnqueueRequest method delivers a specified I/O request to the framework, so that the framework can subsequently add the request to one of the I/O queues that the driver has created for the specified device. |
| [WdfDeviceGetAlignmentRequirement function](nf-wdfdevice-wdfdevicegetalignmentrequirement.md) | The WdfDeviceGetAlignmentRequirement method retrieves a device's address alignment requirement for memory transfer operations. |
| [WdfDeviceGetCharacteristics function](nf-wdfdevice-wdfdevicegetcharacteristics.md) | The WdfDeviceGetCharacteristics method returns device characteristics for a specified device. |
| [WdfDeviceGetDefaultQueue function](nf-wdfdevice-wdfdevicegetdefaultqueue.md) | The WdfDeviceGetDefaultQueue method returns a handle to a device's default I/O queue. |
| [WdfDeviceGetDevicePnpState function](nf-wdfdevice-wdfdevicegetdevicepnpstate.md) | The WdfDeviceGetDevicePnpState method returns the current state of the framework's Plug and Play state machine for a specified device. |
| [WdfDeviceGetDevicePowerPolicyState function](nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md) | The WdfDeviceGetDevicePowerPolicyState method returns the current state of the framework's power policy state machine, for a specified device. |
| [WdfDeviceGetDevicePowerState function](nf-wdfdevice-wdfdevicegetdevicepowerstate.md) | The WdfDeviceGetDevicePowerState method returns the current state of the framework's power state machine, for a specified device. |
| [WdfDeviceGetDeviceStackIoType function](nf-wdfdevice-wdfdevicegetdevicestackiotype.md) | The WdfDeviceGetDeviceStackIoType method retrieves the buffer access methods that the framework is using for a device. |
| [WdfDeviceGetDeviceState function](nf-wdfdevice-wdfdevicegetdevicestate.md) | The WdfDeviceGetDeviceState method retrieves the device state for a specified device. |
| [WdfDeviceGetDriver function](nf-wdfdevice-wdfdevicegetdriver.md) | The WdfDeviceGetDriver method returns a handle to the framework driver object that is associated with a specified framework device object. |
| [WdfDeviceGetFileObject function](nf-wdfdevice-wdfdevicegetfileobject.md) | The WdfDeviceGetFileObject method returns a handle to the framework file object that is associated with a specified WDM file object. |
| [WdfDeviceGetHardwareRegisterMappedAddress function](nf-wdfdevice-wdfdevicegethardwareregistermappedaddress.md) | A driver calls WdfDeviceGetHardwareRegisterMappedAddress to get the user-mode mapped address of the memory resource it mapped previously using WdfDeviceMapIoSpace. |
| [WdfDeviceGetIoTarget function](nf-wdfdevice-wdfdevicegetiotarget.md) | The WdfDeviceGetIoTarget method returns a handle to a function or filter driver's local I/O target, for a specified device. |
| [WdfDeviceGetSystemPowerAction function](nf-wdfdevice-wdfdevicegetsystempoweraction.md) | The WdfDeviceGetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer. |
| [WdfDeviceIndicateWakeStatus function](nf-wdfdevice-wdfdeviceindicatewakestatus.md) | The WdfDeviceIndicateWakeStatus method informs the framework that the calling bus driver has stopped waiting for a specified device to trigger a wake signal on the bus. |
| [WdfDeviceInitAssignName function](nf-wdfdevice-wdfdeviceinitassignname.md) | The WdfDeviceInitAssignName method assigns a device name to a device's device object. |
| [WdfDeviceInitAssignSDDLString function](nf-wdfdevice-wdfdeviceinitassignsddlstring.md) | The WdfDeviceInitAssignSDDLString method assigns a security setting for a device. |
| [WdfDeviceInitAssignWdmIrpPreprocessCallback function](nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback.md) | The WdfDeviceInitAssignWdmIrpPreprocessCallback method registers a callback function to handle an IRP major function code and, optionally, one or more minor function codes that are associated with the major function code. |
| [WdfDeviceInitFree function](nf-wdfdevice-wdfdeviceinitfree.md) | The WdfDeviceInitFree method deallocates a WDFDEVICE_INIT structure. |
| [WdfDeviceInitRegisterPnpStateChangeCallback function](nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback.md) | The WdfDeviceInitRegisterPnpStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state. |
| [WdfDeviceInitRegisterPowerPolicyStateChangeCallback function](nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback.md) | The WdfDeviceInitRegisterPowerPolicyStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power policy state machine changes state. |
| [WdfDeviceInitRegisterPowerStateChangeCallback function](nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback.md) | The WdfDeviceInitRegisterPowerStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power state machine changes state. |
| [WdfDeviceInitSetCharacteristics function](nf-wdfdevice-wdfdeviceinitsetcharacteristics.md) | The WdfDeviceInitSetCharacteristics method sets device characteristics for a specified device. |
| [WdfDeviceInitSetDeviceClass function](nf-wdfdevice-wdfdeviceinitsetdeviceclass.md) | The WdfDeviceInitSetDeviceClass method specifies a GUID that identifies the device's device setup class. |
| [WdfDeviceInitSetDeviceType function](nf-wdfdevice-wdfdeviceinitsetdevicetype.md) | The WdfDeviceInitSetDeviceType method sets the device type for a specified device. |
| [WdfDeviceInitSetExclusive function](nf-wdfdevice-wdfdeviceinitsetexclusive.md) | The WdfDeviceInitSetExclusive method indicates whether a specified device is an exclusive device. |
| [WdfDeviceInitSetFileObjectConfig function](nf-wdfdevice-wdfdeviceinitsetfileobjectconfig.md) | The WdfDeviceInitSetFileObjectConfig method registers event callback functions and sets configuration information for the driver's framework file objects. |
| [WdfDeviceInitSetIoInCallerContextCallback function](nf-wdfdevice-wdfdeviceinitsetioincallercontextcallback.md) | The WdfDeviceInitSetIoInCallerContextCallback method registers a driver's EvtIoInCallerContext event callback function. |
| [WdfDeviceInitSetIoType function](nf-wdfdevice-wdfdeviceinitsetiotype.md) | The WdfDeviceInitSetIoType method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device. |
| [WdfDeviceInitSetIoTypeEx function](nf-wdfdevice-wdfdeviceinitsetiotypeex.md) | The WdfDeviceInitSetIoTypeEx method sets the method or preference for how a driver will access the data buffers that are included in read and write requests, as well as device I/O control requests, for a specified device. |
| [WdfDeviceInitSetPnpPowerEventCallbacks function](nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md) | The WdfDeviceInitSetPnpPowerEventCallbacks method registers a driver's Plug and Play and power management event callback functions. |
| [WdfDeviceInitSetPowerInrush function](nf-wdfdevice-wdfdeviceinitsetpowerinrush.md) | The WdfDeviceInitSetPowerInrush method informs the power manager that the specified device requires an inrush of current when it starts. |
| [WdfDeviceInitSetPowerNotPageable function](nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md) | The WdfDeviceInitSetPowerNotPageable method informs the power manager that the driver will not access pageable data while the system is transitioning between a sleeping state and the working (S0) state. |
| [WdfDeviceInitSetPowerPageable function](nf-wdfdevice-wdfdeviceinitsetpowerpageable.md) | The WdfDeviceInitSetPowerPageable method informs the power manager that the driver must be able to access pageable data while the system is transitioning between a sleeping state and the working (S0) state. |
| [WdfDeviceInitSetPowerPolicyEventCallbacks function](nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md) | The WdfDeviceInitSetPowerPolicyEventCallbacks method registers a driver's power policy event callback functions. |
| [WdfDeviceInitSetPowerPolicyOwnership function](nf-wdfdevice-wdfdeviceinitsetpowerpolicyownership.md) | The WdfDeviceInitSetPowerPolicyOwnership method establishes whether the calling driver is, or is not, the power policy owner for a specified device. |
| [WdfDeviceInitSetReleaseHardwareOrderOnFailure function](nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md) | The WdfDeviceInitSetReleaseHardwareOrderOnFailure method specifies whether the framework calls the driver's EvtDeviceReleaseHardware callback function immediately after device failure, or waits until all child devices have been removed. |
| [WdfDeviceInitSetRemoveLockOptions function](nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md) | The WdfDeviceInitSetRemoveLockOptions method causes the framework to acquire a remove lock before delivering an IRP of any type to the driver. |
| [WdfDeviceInitSetRequestAttributes function](nf-wdfdevice-wdfdeviceinitsetrequestattributes.md) | The WdfDeviceInitSetRequestAttributes method sets object attributes that will be used for all of the framework request objects that the framework delivers to the driver from the device's I/O queues. |
| [WdfDeviceMapIoSpace function](nf-wdfdevice-wdfdevicemapiospace.md) | The WdfDeviceMapIoSpace function maps the given physical address range to system address space and returns a pseudo base address. |
| [WdfDeviceOpenDevicemapKey function](nf-wdfdevice-wdfdeviceopendevicemapkey.md) | The WdfDeviceOpenDevicemapKey method opens the DEVICEMAP key and creates a framework registry-key object that represents the registry key. |
| [WdfDeviceOpenRegistryKey function](nf-wdfdevice-wdfdeviceopenregistrykey.md) | The WdfDeviceOpenRegistryKey method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key. |
| [WdfDevicePostEvent function](nf-wdfdevice-wdfdevicepostevent.md) | The WdfDevicePostEvent method asynchronously notifies applications that are waiting for the specified event from a driver. |
| [WdfDeviceQueryInterfaceProperty function](nf-wdfdevice-wdfdevicequeryinterfaceproperty.md) | The WdfDeviceQueryInterfaceProperty method retrieves a specified device interface property. |
| [WdfDeviceQueryProperty function](nf-wdfdevice-wdfdevicequeryproperty.md) | The WdfDeviceQueryProperty method retrieves a specified device property. |
| [WdfDeviceQueryPropertyEx function](nf-wdfdevice-wdfdevicequerypropertyex.md) | The WdfDeviceQueryPropertyEx method retrieves a specified device property. |
| [WdfDeviceReadFromHardware function](nf-wdfdevice-wdfdevicereadfromhardware.md) | The WdfDeviceReadFromHardware method is used internally by the framework. Do not use. |
| [WdfDeviceRemoveDependentUsageDeviceObject function](nf-wdfdevice-wdfdeviceremovedependentusagedeviceobject.md) | The WdfDeviceRemoveDependentUsageDeviceObject method indicates that a specified device no longer depends on another device when the specified device is used to store special files. |
| [WdfDeviceRemoveRemovalRelationsPhysicalDevice function](nf-wdfdevice-wdfdeviceremoveremovalrelationsphysicaldevice.md) | The WdfDeviceRemoveRemovalRelationsPhysicalDevice method removes a specified device from the list of devices that must be removed when another specified device is removed. |
| [WdfDeviceRetrieveCompanionTarget function](nf-wdfdevice-wdfdeviceretrievecompaniontarget.md) | For internal use only. |
| [WdfDeviceRetrieveDeviceInterfaceString function](nf-wdfdevice-wdfdeviceretrievedeviceinterfacestring.md) | The WdfDeviceRetrieveDeviceInterfaceString method retrieves the symbolic link name that the operating system assigned to a device interface that the driver registered for a specified device. |
| [WdfDeviceRetrieveDeviceName function](nf-wdfdevice-wdfdeviceretrievedevicename.md) | The WdfDeviceRetrieveDeviceName method returns the device name for a specified device. |
| [WdfDeviceSetAlignmentRequirement function](nf-wdfdevice-wdfdevicesetalignmentrequirement.md) | The WdfDeviceSetAlignmentRequirement method registers the driver's preferred address alignment for the data buffers that the device uses during memory transfer operations. |
| [WdfDeviceSetBusInformationForChildren function](nf-wdfdevice-wdfdevicesetbusinformationforchildren.md) | The WdfDeviceSetBusInformationForChildren method sets information about a bus that a bus driver supports. This information is available to the bus's child devices. |
| [WdfDeviceSetCharacteristics function](nf-wdfdevice-wdfdevicesetcharacteristics.md) | The WdfDeviceSetCharacteristics method sets device characteristics for a specified device. |
| [WdfDeviceSetDeviceInterfaceState function](nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md) | The WdfDeviceSetDeviceInterfaceState method enables or disables a device interface for a specified device. |
| [WdfDeviceSetDeviceState function](nf-wdfdevice-wdfdevicesetdevicestate.md) | The WdfDeviceSetDeviceState method sets the device state for a specified device. |
| [WdfDeviceSetFailed function](nf-wdfdevice-wdfdevicesetfailed.md) | The WdfDeviceSetFailed method informs the framework that the driver encountered a hardware or software error that is associated with a specified device. |
| [WdfDeviceSetPnpCapabilities function](nf-wdfdevice-wdfdevicesetpnpcapabilities.md) | The WdfDeviceSetPnpCapabilities method reports a device's Plug and Play capabilities. |
| [WdfDeviceSetPowerCapabilities function](nf-wdfdevice-wdfdevicesetpowercapabilities.md) | The WdfDeviceSetPowerCapabilities method reports a device's power capabilities. |
| [WdfDeviceSetSpecialFileSupport function](nf-wdfdevice-wdfdevicesetspecialfilesupport.md) | The WdfDeviceSetSpecialFileSupport method enables or disables a function driver's support for special files, for the specified device. |
| [WdfDeviceSetStaticStopRemove function](nf-wdfdevice-wdfdevicesetstaticstopremove.md) | The WdfDeviceSetStaticStopRemove method informs the framework whether a device can be stopped and removed. |
| [WdfDeviceUnmapIoSpace function](nf-wdfdevice-wdfdeviceunmapiospace.md) | The WdfDeviceUnmapIoSpace function unmaps a specified range of physical addresses previously mapped by the WdfDeviceMapIoSpace function. |
| [WdfDeviceWdmAssignPowerFrameworkSettings function](nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md) | The WdfDeviceWdmAssignPowerFrameworkSettings method registers power management framework (PoFx) settings for single-component devices. |
| [WdfDeviceWdmDispatchIrp function](nf-wdfdevice-wdfdevicewdmdispatchirp.md) | The WdfDeviceWdmDispatchIrp method returns a dispatched IRP to the framework from EvtDeviceWdmIrpDispatch. |
| [WdfDeviceWdmDispatchIrpToIoQueue function](nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md) | The WdfDeviceWdmDispatchIrpToIoQueue method forwards the IRP to a specified I/O queue. |
| [WdfDeviceWdmDispatchPreprocessedIrp function](nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md) | The WdfDeviceWdmDispatchPreprocessedIrp method returns a preprocessed IRP to the framework. |
| [WdfDeviceWdmGetAttachedDevice function](nf-wdfdevice-wdfdevicewdmgetattacheddevice.md) | The WdfDeviceWdmGetAttachedDevice method returns the next-lower WDM device object in the device stack. |
| [WdfDeviceWdmGetDeviceObject function](nf-wdfdevice-wdfdevicewdmgetdeviceobject.md) | The WdfDeviceWdmGetDeviceObject method returns the Windows Driver Model (WDM) device object that is associated with a specified framework device object. |
| [WdfDeviceWdmGetPhysicalDevice function](nf-wdfdevice-wdfdevicewdmgetphysicaldevice.md) | The WdfDeviceWdmGetPhysicalDevice method retrieves the physical device's WDM PDO from the device stack. |
| [WdfDeviceWriteToHardware function](nf-wdfdevice-wdfdevicewritetohardware.md) | The WdfDeviceWriteToHardware method is used internally by the framework. Do not use. |
| [WdfWdmDeviceGetWdfDeviceHandle function](nf-wdfdevice-wdfwdmdevicegetwdfdevicehandle.md) | The WdfWdmDeviceGetWdfDeviceHandle method returns a handle to the framework device object that is associated with a specified WDM device object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDFDEVICE_WDM_IRP_DISPATCH callback](nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md) | A driver's EvtDeviceWdmIrpDispatch event callback function receives an IRP before the framework processes the IRP. |
| [EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback](nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md) | A driver's EvtDeviceWdmIrpPreprocess event callback function receives an IRP before the framework processes the IRP. |
| [EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback](nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md) | The EvtDeviceWdmPostPoFxRegisterDevice callback function performs device-specific operations after the framework has registered with the power framework. |
| [EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback](nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md) | The EvtDeviceWdmPrePoFxUnregisterDevice callback function performs device-specific operations before the framework deletes a specified registration with the power framework. |
| [EVT_WDF_DEVICE_ARM_WAKE_FROM_S0 callback](nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md) | A driver's EvtDeviceArmWakeFromS0 event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0). |
| [EVT_WDF_DEVICE_ARM_WAKE_FROM_SX callback](nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md) | A driver's EvtDeviceArmWakeFromSx event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. |
| [EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON callback](nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason.md) | A driver's EvtDeviceArmWakeFromSxWithReason event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. |
| [EVT_WDF_DEVICE_D0_ENTRY callback](nc-wdfdevice-evt_wdf_device_d0_entry.md) | A driver's EvtDeviceD0Entry event callback function performs operations that are needed when the driver's device enters the D0 power state. |
| [EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED callback](nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled.md) | A driver's EvtDeviceD0EntryPostInterruptsEnabled event callback function performs device-specific operations that are required after the driver has enabled the device's hardware interrupts. |
| [EVT_WDF_DEVICE_D0_EXIT callback](nc-wdfdevice-evt_wdf_device_d0_exit.md) | A driver's EvtDeviceD0Exit event callback function performs operations that are needed when the driver's device leaves the D0 power state. |
| [EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback](nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md) | A driver's EvtDeviceD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts. |
| [EVT_WDF_DEVICE_DISARM_WAKE_FROM_S0 callback](nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md) | A driver's EvtDeviceDisarmWakeFromS0 event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0). |
| [EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback](nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md) | A driver's EvtDeviceDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states. |
| [EVT_WDF_DEVICE_FILE_CREATE callback](nc-wdfdevice-evt_wdf_device_file_create.md) | A driver's EvtDeviceFileCreate callback function handles operations that must be performed when an application requests access to a device. |
| [EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback](nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md) | A driver's EvtDevicePnpStateChange event callback function informs the driver that a device's Plug and Play (PnP) state machine is moving from one state to another. |
| [EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback](nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification.md) | A driver's EvtDevicePowerPolicyStateChange event callback function informs the driver that a device's power policy state machine is moving from one state to another. |
| [EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback](nc-wdfdevice-evt_wdf_device_power_state_change_notification.md) | A driver's EvtDevicePowerStateChange event callback function informs the driver that a device's power state machine is moving from one state to another. |
| [EVT_WDF_DEVICE_PREPARE_HARDWARE callback](nc-wdfdevice-evt_wdf_device_prepare_hardware.md) | A driver's EvtDevicePrepareHardware event callback function performs any operations that are needed to make a device accessible to the driver. |
| [EVT_WDF_DEVICE_QUERY_REMOVE callback](nc-wdfdevice-evt_wdf_device_query_remove.md) | A driver's EvtDeviceQueryRemove event callback function determines whether a specified device can be stopped and removed. |
| [EVT_WDF_DEVICE_QUERY_STOP callback](nc-wdfdevice-evt_wdf_device_query_stop.md) | A driver's EvtDeviceQueryStop event callback function determines whether a specified device can be stopped so that the PnP manager can redistribute system hardware resources. |
| [EVT_WDF_DEVICE_RELATIONS_QUERY callback](nc-wdfdevice-evt_wdf_device_relations_query.md) | A driver's EvtDeviceRelationsQuery event callback reports changes in the relationships among devices that are supported by the driver. |
| [EVT_WDF_DEVICE_RELEASE_HARDWARE callback](nc-wdfdevice-evt_wdf_device_release_hardware.md) | A driver's EvtDeviceReleaseHardware event callback function performs operations that are needed when a device is no longer accessible. |
| [EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP callback](nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md) | A driver's EvtDeviceSelfManagedIoCleanup event callback function handles deallocation activity for the device's self-managed I/O operations, after a device has been removed. |
| [EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback](nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md) | A driver's EvtDeviceSelfManagedIoFlush event callback function handles flush activity for the device's self-managed I/O operations. |
| [EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT callback](nc-wdfdevice-evt_wdf_device_self_managed_io_init.md) | A driver's EvtDeviceSelfManagedIoInit event callback function initializes and starts the device's self-managed I/O operations. |
| [EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback](nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md) | A driver's EvtDeviceSelfManagedIoRestart event callback function restarts a device's self-managed I/O operations. |
| [EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback](nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md) | A driver's EvtDeviceSelfManagedIoSuspend event callback function suspends a device's self-managed I/O operations. |
| [EVT_WDF_DEVICE_SURPRISE_REMOVAL callback](nc-wdfdevice-evt_wdf_device_surprise_removal.md) | A driver's EvtDeviceSurpriseRemoval event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that the device has failed. |
| [EVT_WDF_DEVICE_USAGE_NOTIFICATION callback](nc-wdfdevice-evt_wdf_device_usage_notification.md) | A driver's EvtDeviceUsageNotification event callback function informs the driver when a device is being used for special files. |
| [EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback](nc-wdfdevice-evt_wdf_device_usage_notification_ex.md) | A driver's EvtDeviceUsageNotificationEx event callback function determines whether a device can support a special file type. |
| [EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback](nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered.md) | A driver's EvtDeviceWakeFromS0Triggered event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal. |
| [EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED callback](nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md) | A driver's EvtDeviceWakeFromSxTriggered event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal. |
| [EVT_WDF_FILE_CLEANUP callback](nc-wdfdevice-evt_wdf_file_cleanup.md) | A driver's EvtFileCleanup callback function handles operations that must be performed when an application is closing all accesses to a device. |
| [EVT_WDF_FILE_CLOSE callback](nc-wdfdevice-evt_wdf_file_close.md) | A driver's EvtFileClose callback function handles operations that must be performed when all of an application's accesses to a device have been closed. |
| [EVT_WDF_IO_IN_CALLER_CONTEXT callback](nc-wdfdevice-evt_wdf_io_in_caller_context.md) | A driver's EvtIoInCallerContext event callback function preprocesses an I/O request before the framework places it into an I/O queue. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_DEVICE_INTERFACE_PROPERTY_DATA structure](ns-wdfdevice-_wdf_device_interface_property_data.md) | The WDF_DEVICE_INTERFACE_PROPERTY_DATA structure describes a device interface property. |
| [_WDF_DEVICE_PNP_CAPABILITIES structure](ns-wdfdevice-_wdf_device_pnp_capabilities.md) | The WDF_DEVICE_PNP_CAPABILITIES structure describes a device's Plug and Play capabilities. |
| [_WDF_DEVICE_PNP_NOTIFICATION_DATA structure](ns-wdfdevice-_wdf_device_pnp_notification_data.md) | The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine. |
| [_WDF_DEVICE_POWER_CAPABILITIES structure](ns-wdfdevice-_wdf_device_power_capabilities.md) | The WDF_DEVICE_POWER_CAPABILITIES structure describes a device's power capabilities. |
| [_WDF_DEVICE_POWER_NOTIFICATION_DATA structure](ns-wdfdevice-_wdf_device_power_notification_data.md) | The WDF_DEVICE_POWER_NOTIFICATION_DATA structure describes a state change within a device's power state machine. |
| [_WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure](ns-wdfdevice-_wdf_device_power_policy_idle_settings.md) | The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure contains driver-supplied information that the framework uses when a device is idle and the system is in the system working state (S0). |
| [_WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA structure](ns-wdfdevice-_wdf_device_power_policy_notification_data.md) | The WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA structure describes a state change within a device's power policy state machine. |
| [_WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure](ns-wdfdevice-_wdf_device_power_policy_wake_settings.md) | The WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure contains driver-supplied information about a device's ability to wake itself and the system, when both are in a low-power state. |
| [_WDF_DEVICE_PROPERTY_DATA structure](ns-wdfdevice-_wdf_device_property_data.md) | The WDF_DEVICE_PROPERTY_DATA structure describes a device property. |
| [_WDF_DEVICE_STATE structure](ns-wdfdevice-_wdf_device_state.md) | The WDF_DEVICE_STATE structure specifies a device's Plug and Play state. |
| [_WDF_FILEOBJECT_CONFIG structure](ns-wdfdevice-_wdf_fileobject_config.md) | The WDF_FILEOBJECT_CONFIG structure contains configuration information of a driver's framework file objects. |
| [_WDF_IO_TYPE_CONFIG structure](ns-wdfdevice-_wdf_io_type_config.md) | The WDF_IO_TYPE_CONFIG structure specifies the driver's preferred buffer access method for read and write requests, and for device I/O control requests. |
| [_WDF_PNPPOWER_EVENT_CALLBACKS structure](ns-wdfdevice-_wdf_pnppower_event_callbacks.md) | The WDF_PNPPOWER_EVENT_CALLBACKS structure contains pointers to a driver's Plug and Play and power event callback functions. |
| [_WDF_POWER_FRAMEWORK_SETTINGS structure](ns-wdfdevice-_wdf_power_framework_settings.md) | The WDF_POWER_FRAMEWORK_SETTINGS structure describes power management framework (PoFx) settings for single-component devices. |
| [_WDF_POWER_POLICY_EVENT_CALLBACKS structure](ns-wdfdevice-_wdf_power_policy_event_callbacks.md) | The WDF_POWER_POLICY_EVENT_CALLBACKS structure contains pointers to a driver's power policy event callback functions. |
| [_WDF_REMOVE_LOCK_OPTIONS structure](ns-wdfdevice-_wdf_remove_lock_options.md) | The WDF_REMOVE_LOCK_OPTIONS structure specifies options for acquiring a remove lock before delivering an IRP to the driver. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_DEVICE_FAILED_ACTION enumeration](ne-wdfdevice-_wdf_device_failed_action.md) | The WDF_DEVICE_FAILED_ACTION enumeration identifies the action that the framework will take when a driver reports an unrecoverable software or hardware failure. |
| [_WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration](ne-wdfdevice-_wdf_device_hwaccess_target_size.md) | The WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration is used internally by the framework. Do not use. |
| [_WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration](ne-wdfdevice-_wdf_device_hwaccess_target_type.md) | The WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration is used internally by the framework. Do not use. |
| [_WDF_DEVICE_IO_TYPE enumeration](ne-wdfdevice-_wdf_device_io_type.md) | The WDF_DEVICE_IO_TYPE enumeration is used to specify a method for accessing data buffers. |
| [_WDF_DEVICE_PNP_STATE enumeration](ne-wdfdevice-_wdf_device_pnp_state.md) | The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter. |
| [_WDF_DEVICE_POWER_POLICY_STATE enumeration](ne-wdfdevice-_wdf_device_power_policy_state.md) | The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter. |
| [_WDF_DEVICE_POWER_STATE enumeration](ne-wdfdevice-_wdf_device_power_state.md) | The WDF_DEVICE_POWER_STATE enumeration identifies all of the states that the framework's power state machine can enter. |
| [_WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS enumeration](ne-wdfdevice-_wdf_dispatch_irp_to_io_queue_flags.md) | The WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS enumeration type defines flags that the driver can specify when it calls WdfDeviceWdmDispatchIrpToIoQueue. |
| [_WDF_EVENT_TYPE enumeration](ne-wdfdevice-_wdf_event_type.md) | The WDF_EVENT_TYPE enumeration specifies. |
| [_WDF_FILEOBJECT_CLASS enumeration](ne-wdfdevice-_wdf_fileobject_class.md) | The WDF_FILEOBJECT_CLASS enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open. |
| [_WDF_POWER_DEVICE_STATE enumeration](ne-wdfdevice-_wdf_power_device_state.md) | The WDF_POWER_DEVICE_STATE enumeration identifies the device power states that a device might support. |
| [_WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration](ne-wdfdevice-_wdf_power_policy_idle_timeout_constants.md) | The WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration is reserved for internal use. |
| [_WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration](ne-wdfdevice-_wdf_power_policy_idle_timeout_type.md) | The WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration identifies how the idle timeout for a device is determined. |
| [_WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration](ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities.md) | The WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling. |
| [_WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration](ne-wdfdevice-_wdf_power_policy_s0_idle_user_control.md) | The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state. |
| [_WDF_POWER_POLICY_SX_WAKE_USER_CONTROL enumeration](ne-wdfdevice-_wdf_power_policy_sx_wake_user_control.md) | The WDF_POWER_POLICY_SX_WAKE_USER_CONTROL enumeration identifies whether a user can control a device's ability to wake the system from a low system power state. |
| [_WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration](ne-wdfdevice-_wdf_release_hardware_order_on_failure.md) | The WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration specifies when the framework calls a driver's EvtDeviceReleaseHardware callback function. |
| [_WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration](ne-wdfdevice-_wdf_remove_lock_options_flags.md) | The WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REMOVE_LOCK_OPTIONS structure. |
| [_WDF_SPECIAL_FILE_TYPE enumeration](ne-wdfdevice-_wdf_special_file_type.md) | The WDF_SPECIAL_FILE_TYPE enumeration identifies special file types that a device can support. |
| [_WDF_STATE_NOTIFICATION_TYPE enumeration](ne-wdfdevice-_wdf_state_notification_type.md) | The WDF_STATE_NOTIFICATION_TYPE enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [WdfDeviceResumeIdle macro](nf-wdfdevice-wdfdeviceresumeidle.md) | The WdfDeviceResumeIdle method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle. |
| [WdfDeviceStopIdle macro](nf-wdfdevice-wdfdevicestopidle.md) | The WdfDeviceStopIdle method informs the framework that the specified device must be placed in its working (D0) power state. |
