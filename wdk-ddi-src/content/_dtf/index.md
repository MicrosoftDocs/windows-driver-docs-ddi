---
UID: TP:dtf
ms.assetid: d5452dd2-c8e3-30e9-8760-2f451dbe92d2
ms.author: windowsdriverdev
ms.date: 04/02/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Dtf

## -description

Overview of the Dtf technology.

To develop Dtf, you need these headers:

 * [comtracing.h](..\comtracing\index.md)
 * [interruption.h](..\interruption\index.md)
 * [itestresource.h](..\itestresource\index.md)
 * [log.h](..\log\index.md)
 * [logcontext.h](..\logcontext\index.md)
 * [logcontroller.h](..\logcontroller\index.md)
 * [logtestresults.h](..\logtestresults\index.md)
 * [preservelasterror.h](..\preservelasterror\index.md)
 * [resourcelist.h](..\resourcelist\index.md)
 * [runtimeparameters.h](..\runtimeparameters\index.md)
 * [screencapture.h](..\screencapture\index.md)
 * [te.common.h](..\te.common\index.md)
 * [testdata.h](..\testdata\index.md)
 * [testnotification.h](..\testnotification\index.md)
 * [throw.h](..\throw\index.md)
 * [tracing.h](..\tracing\index.md)
 * [verify.h](..\verify\index.md)
 * [wdtf.h](..\wdtf\index.md)
 * [wdtf.idl](..\wdtf\index.md)
 * [wdtfdriverpackageaction.h](..\wdtfdriverpackageaction\index.md)
 * [wdtfdriverpackageaction.idl](..\wdtfdriverpackageaction\index.md)
 * [wdtfdriversetupdeviceaction.h](..\wdtfdriversetupdeviceaction\index.md)
 * [wdtfdriversetupdeviceaction.idl](..\wdtfdriversetupdeviceaction\index.md)
 * [wdtfdriversetupsystemaction.h](..\wdtfdriversetupsystemaction\index.md)
 * [wdtfedtaction.h](..\wdtfedtaction\index.md)
 * [wdtfinterfaces.h](..\wdtfinterfaces\index.md)
 * [wdtfinterfacessup.h](..\wdtfinterfacessup\index.md)
 * [wdtflogging.h](..\wdtflogging\index.md)
 * [wdtfpnpaction.h](..\wdtfpnpaction\index.md)
 * [wdtfsimulatedbatterysystemaction.h](..\wdtfsimulatedbatterysystemaction\index.md)
 * [wdtfsystemaction.h](..\wdtfsystemaction\index.md)
 * [wex.common.h](..\wex.common\index.md)
 * [wex.logger.h](..\wex.logger\index.md)
 * [wexassert.h](..\wexassert\index.md)
 * [wexdebug.h](..\wexdebug\index.md)
 * [wexexception.h](..\wexexception\index.md)
 * [wexlogtrace.h](..\wexlogtrace\index.md)
 * [wexstring.h](..\wexstring\index.md)
 * [wextestclass.h](..\wextestclass\index.md)
 * [wextypes.h](..\wextypes\index.md)
 * [wppdefs.h](..\wppdefs\index.md)



## Enumerations

| Title   | Description   |
| ---- |:---- |
| [__MIDL___MIDL_itf_wdtf_0000_0001_0001 enumeration](..\wppdefs\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md) | The TTraceLevel enumeration defines a set of levels for tracing in WDTF. The meaning on each level depends on registry settings for the ITracer interface. |
| [__MIDL___MIDL_itf_wdtf_0000_0001_0001 enumeration](..\wppdefs\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md) | The TTraceLevel enumeration defines a set of levels for tracing in WDTF. The meaning on each level depends on registry settings for the ITracer interface. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAction interface](..\wppdefs\nn-wdtf-iaction.md) | The IAction interfaces are plug-ins that can control an instance of the IWDTFTarget2 interface. |
| [IAction interface](..\wppdefs\nn-wdtf-iaction.md) | The IAction interfaces are plug-ins that can control an instance of the IWDTFTarget2 interface. |
| [ITracer interface](..\wppdefs\nn-wdtf-itracer.md) | The ITracer interface enables individual instances of every WDTF interface to determine the specific tracing settings for a given implementation coclass. These settings are recorded in the registry. |
| [ITracer interface](..\wppdefs\nn-wdtf-itracer.md) | The ITracer interface enables individual instances of every WDTF interface to determine the specific tracing settings for a given implementation coclass. These settings are recorded in the registry. |
| [ITracing interface](..\wppdefs\nn-wdtf-itracing.md) | The ITracing interface sets an object's TTraceLevel value. This interface is a base interface for most of the WDTF interfaces. |
| [ITracing interface](..\wppdefs\nn-wdtf-itracing.md) | The ITracing interface sets an object's TTraceLevel value. This interface is a base interface for most of the WDTF interfaces. |
| [IWDTF2 interface](..\wppdefs\nn-wdtf-iwdtf2.md) | Defines properties for the WDTF collection. |
| [IWDTF2 interface](..\wppdefs\nn-wdtf-iwdtf2.md) | Defines properties for the WDTF collection. |
| [IWDTFAction2 interface](..\wppdefs\nn-wdtf-iwdtfaction2.md) | Defines operations and properties that can control an instance of the IWDTFTarget2 interface. |
| [IWDTFAction2 interface](..\wppdefs\nn-wdtf-iwdtfaction2.md) | Defines operations and properties that can control an instance of the IWDTFTarget2 interface. |
| [IWDTFActions2 interface](..\wppdefs\nn-wdtf-iwdtfactions2.md) | Defines operations and properties for the collection of actions that the IWDTFTargets |
| [IWDTFActions2 interface](..\wppdefs\nn-wdtf-iwdtfactions2.md) | Defines operations and properties for the collection of actions that the IWDTFTargets |
| [IWDTFCONFIG2 interface](..\wppdefs\nn-wdtf-iwdtfconfig2.md) | Defines operations that control WDTF objects within a test script. |
| [IWDTFCONFIG2 interface](..\wppdefs\nn-wdtf-iwdtfconfig2.md) | Defines operations that control WDTF objects within a test script. |
| [IWDTFDeviceDepot2 interface](..\wppdefs\nn-wdtf-iwdtfdevicedepot2.md) | Defines properties and operations for the collection of devices on a computer. |
| [IWDTFDeviceDepot2 interface](..\wppdefs\nn-wdtf-iwdtfdevicedepot2.md) | Defines properties and operations for the collection of devices on a computer. |
| [IWDTFDriverPackageAction2 interface](..\wppdefs\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md) | Defines operations and properties that represent a driver package for imported and pre-imported driver packages. |
| [IWDTFDriverPackageAction2 interface](..\wppdefs\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md) | Defines operations and properties that represent a driver package for imported and pre-imported driver packages. |
| [IWDTFDriverSetupAction2 interface](..\wppdefs\nn-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2.md) | Defines operations that control the target device during driver setup. |
| [IWDTFDriverSetupAction2 interface](..\wppdefs\nn-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2.md) | Defines operations that control the target device during driver setup. |
| [IWDTFDriverSetupSystemAction2 interface](..\wppdefs\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md) | Defines operations that control the system during driver setup. |
| [IWDTFEnhancedDeviceTestSupportAction2 interface](..\wppdefs\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2.md) | Defines operations and properties that support the Enhanced Device Test (EDT) filter driver. |
| [IWDTFEnhancedDeviceTestSupportActions2 interface](..\wppdefs\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2.md) | Defines operations and properties that support the collection of Enhanced Device Test (EDT) actions. |
| [IWDTFLOG2 interface](..\wppdefs\nn-wdtf-iwdtflog2.md) | Defines operations that enable the test case author to add to the WDTF test log. |
| [IWDTFLOG2 interface](..\wppdefs\nn-wdtf-iwdtflog2.md) | Defines operations that enable the test case author to add to the WDTF test log. |
| [IWDTFLongNumbers2 interface](..\wppdefs\nn-wdtf-iwdtflongnumbers2.md) | Defines operations and properties for a collection of long numbers. |
| [IWDTFLongNumbers2 interface](..\wppdefs\nn-wdtf-iwdtflongnumbers2.md) | Defines operations and properties for a collection of long numbers. |
| [IWDTFNumbers2 interface](..\wppdefs\nn-wdtf-iwdtfnumbers2.md) | Defines operations and properties for a collection of numbers. |
| [IWDTFNumbers2 interface](..\wppdefs\nn-wdtf-iwdtfnumbers2.md) | Defines operations and properties for a collection of numbers. |
| [IWDTFPNPAction2 interface](..\wppdefs\nn-wdtfpnpaction-iwdtfpnpaction2.md) | Defines operations and properties for the Plug and Play (PNP) device-related test interfaces. |
| [IWDTFPNPActions2 interface](..\wppdefs\nn-wdtfpnpaction-iwdtfpnpactions2.md) | Defines operations and properties for the collection of Plug and Play (PNP) device-related test interfaces. |
| [IWDTFSimpleIOEx2 interface](..\wppdefs\nn-wdtfinterfaces-iwdtfsimpleioex2.md) | Defines operations for a simple synchronous I/O functionality test. |
| [IWDTFSimpleIOStressAction2 interface](..\wppdefs\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md) | Defines operations for a simple asynchronous I/O functionality test. |
| [IWDTFSimpleIOStressActions2 interface](..\wppdefs\nn-wdtfinterfaces-iwdtfsimpleiostressactions2.md) | Defines operations for a collection of simple asynchronous I/O functionality tests. |
| [IWDTFSimulatedBatterySystemAction interface](..\wppdefs\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md) | IWDTFSimulatedBatterySystemAction Interface |
| [IWDTFStrings2 interface](..\wppdefs\nn-wdtf-iwdtfstrings2.md) | Defines operations and properties for a collection of strings. |
| [IWDTFStrings2 interface](..\wppdefs\nn-wdtf-iwdtfstrings2.md) | Defines operations and properties for a collection of strings. |
| [IWDTFSystemAction2 interface](..\wppdefs\nn-wdtfsystemaction-iwdtfsystemaction2.md) | Defines operations and properties that support driver testing. |
| [IWDTFSystemDepot2 interface](..\wppdefs\nn-wdtf-iwdtfsystemdepot2.md) | Defines operations and properties for the SystemDepot - the object that represents the local computer. |
| [IWDTFSystemDepot2 interface](..\wppdefs\nn-wdtf-iwdtfsystemdepot2.md) | Defines operations and properties for the SystemDepot - the object that represents the local computer. |
| [IWDTFTarget2 interface](..\wppdefs\nn-wdtf-iwdtftarget2.md) | Defines operations and properties for a testable item. |
| [IWDTFTarget2 interface](..\wppdefs\nn-wdtf-iwdtftarget2.md) | Defines operations and properties for a testable item. |
| [IWDTFTargets2 interface](..\wppdefs\nn-wdtf-iwdtftargets2.md) | Defines properties and operations for the collection. |
| [IWDTFTargets2 interface](..\wppdefs\nn-wdtf-iwdtftargets2.md) | Defines properties and operations for the collection. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IAction::SetTarget method](..\wppdefs\nf-wdtf-iaction-settarget.md) | The SetTarget method is used internally by WDTF. Do not call this method directly. |
| [IAction::SetTarget method](..\wppdefs\nf-wdtf-iaction-settarget.md) | The SetTarget method is used internally by WDTF. Do not call this method directly. |
| [ITracer::GetBits method](..\wppdefs\nf-wdtf-itracer-getbits.md) | The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass. |
| [ITracer::GetBits method](..\wppdefs\nf-wdtf-itracer-getbits.md) | The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass. |
| [ITracing::SetTraceLevel method](..\wppdefs\nf-wdtf-itracing-settracelevel.md) | The SetTraceLevel method sets the tracing level for an object. |
| [ITracing::SetTraceLevel method](..\wppdefs\nf-wdtf-itracing-settracelevel.md) | The SetTraceLevel method sets the tracing level for an object. |
| [IWDTF2::get_Config method](..\wppdefs\nf-wdtf-iwdtf2-get_config.md) | Gets the WDTF configuration object. |
| [IWDTF2::get_Config method](..\wppdefs\nf-wdtf-iwdtf2-get_config.md) | Gets the WDTF configuration object. |
| [IWDTF2::get_DeviceDepot method](..\wppdefs\nf-wdtf-iwdtf2-get_devicedepot.md) | Gets the DeviceDepot object. |
| [IWDTF2::get_DeviceDepot method](..\wppdefs\nf-wdtf-iwdtf2-get_devicedepot.md) | Gets the DeviceDepot object. |
| [IWDTF2::get_Log method](..\wppdefs\nf-wdtf-iwdtf2-get_log.md) | Gets the WDTF log object. |
| [IWDTF2::get_Log method](..\wppdefs\nf-wdtf-iwdtf2-get_log.md) | Gets the WDTF log object. |
| [IWDTF2::get_SystemDepot method](..\wppdefs\nf-wdtf-iwdtf2-get_systemdepot.md) | Gets the SystemDepot object. |
| [IWDTF2::get_SystemDepot method](..\wppdefs\nf-wdtf-iwdtf2-get_systemdepot.md) | Gets the SystemDepot object. |
| [IWDTFAction2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-disableobjecterrorlogging.md) | Disables object error logging for the action. |
| [IWDTFAction2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-disableobjecterrorlogging.md) | Disables object error logging for the action. |
| [IWDTFAction2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-disableobjectlogging.md) | Disables object logging for the action. |
| [IWDTFAction2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-disableobjectlogging.md) | Disables object logging for the action. |
| [IWDTFAction2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-enableobjecterrorlogging.md) | Enables object error logging for the action. |
| [IWDTFAction2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-enableobjecterrorlogging.md) | Enables object error logging for the action. |
| [IWDTFAction2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-enableobjectlogging.md) | Enables object logging for the action. |
| [IWDTFAction2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfaction2-enableobjectlogging.md) | Enables object logging for the action. |
| [IWDTFAction2::GetStatus method](..\wppdefs\nf-wdtf-iwdtfaction2-getstatus.md) | Returns the status code for the last operation. |
| [IWDTFAction2::GetStatus method](..\wppdefs\nf-wdtf-iwdtfaction2-getstatus.md) | Returns the status code for the last operation. |
| [IWDTFAction2::GetStatusString method](..\wppdefs\nf-wdtf-iwdtfaction2-getstatusstring.md) | Returns the status for the last operation as a string. |
| [IWDTFAction2::GetStatusString method](..\wppdefs\nf-wdtf-iwdtfaction2-getstatusstring.md) | Returns the status for the last operation as a string. |
| [IWDTFAction2::IsStatusSuccess method](..\wppdefs\nf-wdtf-iwdtfaction2-isstatussuccess.md) | Gets a value that indicates whether the last operation was successful. |
| [IWDTFAction2::IsStatusSuccess method](..\wppdefs\nf-wdtf-iwdtfaction2-isstatussuccess.md) | Gets a value that indicates whether the last operation was successful. |
| [IWDTFAction2::get_Target method](..\wppdefs\nf-wdtf-iwdtfaction2-get_target.md) | Gets the target to which this action refers. |
| [IWDTFAction2::get_Target method](..\wppdefs\nf-wdtf-iwdtfaction2-get_target.md) | Gets the target to which this action refers. |
| [IWDTFActions2::Add method](..\wppdefs\nf-wdtf-iwdtfactions2-add.md) | Add a single action to the collection. |
| [IWDTFActions2::Add method](..\wppdefs\nf-wdtf-iwdtfactions2-add.md) | Add a single action to the collection. |
| [IWDTFActions2::Clear method](..\wppdefs\nf-wdtf-iwdtfactions2-clear.md) | Removes all items from the collection. |
| [IWDTFActions2::Clear method](..\wppdefs\nf-wdtf-iwdtfactions2-clear.md) | Removes all items from the collection. |
| [IWDTFActions2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-disableobjecterrorlogging.md) | Disable object error logging for all actions in the collection. |
| [IWDTFActions2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-disableobjecterrorlogging.md) | Disable object error logging for all actions in the collection. |
| [IWDTFActions2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-disableobjectlogging.md) | Disable object logging for all actions in the collection. |
| [IWDTFActions2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-disableobjectlogging.md) | Disable object logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-enableobjecterrorlogging.md) | Enable object error logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-enableobjecterrorlogging.md) | Enable object error logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-enableobjectlogging.md) | Enable object logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfactions2-enableobjectlogging.md) | Enable object logging for all actions in the collection. |
| [IWDTFActions2::Remove method](..\wppdefs\nf-wdtf-iwdtfactions2-remove.md) | Remove an action from the collection. |
| [IWDTFActions2::Remove method](..\wppdefs\nf-wdtf-iwdtfactions2-remove.md) | Remove an action from the collection. |
| [IWDTFActions2::get_Count method](..\wppdefs\nf-wdtf-iwdtfactions2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFActions2::get_Count method](..\wppdefs\nf-wdtf-iwdtfactions2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFActions2::get_Item method](..\wppdefs\nf-wdtf-iwdtfactions2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFActions2::get_Item method](..\wppdefs\nf-wdtf-iwdtfactions2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFActions2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfactions2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFActions2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfactions2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFCONFIG2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-disableobjecterrorlogging.md) | Disables object error logging for all objects. |
| [IWDTFCONFIG2::DisableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-disableobjecterrorlogging.md) | Disables object error logging for all objects. |
| [IWDTFCONFIG2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-disableobjectlogging.md) | Disables object logging for all objects. |
| [IWDTFCONFIG2::DisableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-disableobjectlogging.md) | Disables object logging for all objects. |
| [IWDTFCONFIG2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-enableobjecterrorlogging.md) | Enables object error logging for all objects. |
| [IWDTFCONFIG2::EnableObjectErrorLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-enableobjecterrorlogging.md) | Enables object error logging for all objects. |
| [IWDTFCONFIG2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-enableobjectlogging.md) | Enables object logging for all objects. |
| [IWDTFCONFIG2::EnableObjectLogging method](..\wppdefs\nf-wdtf-iwdtfconfig2-enableobjectlogging.md) | Enables object logging for all objects. |
| [IWDTFDeviceDepot2::Query method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-query.md) | Returns a subset of the devices in the DeviceDepot. |
| [IWDTFDeviceDepot2::Query method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-query.md) | Returns a subset of the devices in the DeviceDepot. |
| [IWDTFDeviceDepot2::QuerySingle method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-querysingle.md) | Returns a single target device from the DeviceDepot. |
| [IWDTFDeviceDepot2::QuerySingle method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-querysingle.md) | Returns a single target device from the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Count method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Count method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Item method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Item method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFDeviceDepot2::get_RootDevice method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_rootdevice.md) | Gets the root device. |
| [IWDTFDeviceDepot2::get_RootDevice method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_rootdevice.md) | Gets the root device. |
| [IWDTFDeviceDepot2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFDeviceDepot2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFDeviceDepot2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFDeviceDepot2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfdevicedepot2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFDriverPackageAction2::Compare method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-compare.md) | Compares two driver packages. |
| [IWDTFDriverPackageAction2::Compare method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-compare.md) | Compares two driver packages. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordevicethatcanusepackage.md) | Returns an SDEL statement that queries for all devices that can use the driver package. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordevicethatcanusepackage.md) | Returns an SDEL statement that queries for all devices that can use the driver package. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordeviceusingpackage.md) | Returns an SDEL statement that queries for all devices that use the driver package. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordeviceusingpackage.md) | Returns an SDEL statement that queries for all devices that use the driver package. |
| [IWDTFDriverPackageAction2::SetPackageInfFileName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-setpackageinffilename.md) | Sets the pre-imported driver package path. |
| [IWDTFDriverPackageAction2::SetPackageInfFileName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-setpackageinffilename.md) | Sets the pre-imported driver package path. |
| [IWDTFDriverPackageAction2::get_CatalogFile method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_catalogfile.md) | Gets the catalog file name. |
| [IWDTFDriverPackageAction2::get_CatalogFile method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_catalogfile.md) | Gets the catalog file name. |
| [IWDTFDriverPackageAction2::get_ClassGuid method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classguid.md) | Gets the class GUID. |
| [IWDTFDriverPackageAction2::get_ClassGuid method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classguid.md) | Gets the class GUID. |
| [IWDTFDriverPackageAction2::get_ClassName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classname.md) | Gets the class name. |
| [IWDTFDriverPackageAction2::get_ClassName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classname.md) | Gets the class name. |
| [IWDTFDriverPackageAction2::get_Date method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_date.md) | Gets the driver package date. |
| [IWDTFDriverPackageAction2::get_Date method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_date.md) | Gets the driver package date. |
| [IWDTFDriverPackageAction2::get_DigitalSigner method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_digitalsigner.md) | Gets the digital signer. |
| [IWDTFDriverPackageAction2::get_DigitalSigner method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_digitalsigner.md) | Gets the digital signer. |
| [IWDTFDriverPackageAction2::get_HasCatalog method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_hascatalog.md) | Gets a value that indicates whether the driver package has a catalog. |
| [IWDTFDriverPackageAction2::get_HasCatalog method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_hascatalog.md) | Gets a value that indicates whether the driver package has a catalog. |
| [IWDTFDriverPackageAction2::get_InfFileName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_inffilename.md) | Gets the INF file name. |
| [IWDTFDriverPackageAction2::get_InfFileName method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_inffilename.md) | Gets the INF file name. |
| [IWDTFDriverPackageAction2::get_IsDigitalSigned method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isdigitalsigned.md) | Gets a value that indicates whether the driver package is signed. |
| [IWDTFDriverPackageAction2::get_IsDigitalSigned method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isdigitalsigned.md) | Gets a value that indicates whether the driver package is signed. |
| [IWDTFDriverPackageAction2::get_IsImported method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isimported.md) | Gets a value that indicates whether the driver package is imported. |
| [IWDTFDriverPackageAction2::get_IsImported method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isimported.md) | Gets a value that indicates whether the driver package is imported. |
| [IWDTFDriverPackageAction2::get_Provider method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_provider.md) | Gets the driver package provider. |
| [IWDTFDriverPackageAction2::get_Provider method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_provider.md) | Gets the driver package provider. |
| [IWDTFDriverPackageAction2::get_Version method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_version.md) | Gets the driver package version. |
| [IWDTFDriverPackageAction2::get_Version method](..\wppdefs\nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_version.md) | Gets the driver package version. |
| [IWDTFDriverSetupAction2::UnInstallDriverPermanently method](..\wppdefs\nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-uninstalldriverpermanently.md) | Uninstalls the current driver for the target device. |
| [IWDTFDriverSetupAction2::UnInstallDriverPermanently method](..\wppdefs\nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-uninstalldriverpermanently.md) | Uninstalls the current driver for the target device. |
| [IWDTFDriverSetupAction2::UpdateDriver method](..\wppdefs\nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-updatedriver.md) | Updates the target device with a driver from the driver package. |
| [IWDTFDriverSetupAction2::UpdateDriver method](..\wppdefs\nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-updatedriver.md) | Updates the target device with a driver from the driver package. |
| [IWDTFDriverSetupSystemAction2::ClearTriageLogs method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-cleartriagelogs.md) | Clears the system device setup triage logs. |
| [IWDTFDriverSetupSystemAction2::ImportDriverPackage method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-importdriverpackage.md) | Imports a driver packge to the system driver store. |
| [IWDTFDriverSetupSystemAction2::IsImported method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-isimported.md) | Returns a value that indicates whether a package has already been imported. |
| [IWDTFDriverSetupSystemAction2::RemoveDriverPackage method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-removedriverpackage.md) | Removes a driver package from the driver store. |
| [IWDTFDriverSetupSystemAction2::RescanAllDevices method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-rescanalldevices.md) | Re-enumerates all devices in the system. |
| [IWDTFDriverSetupSystemAction2::SnapTriageLogs method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-snaptriagelogs.md) | Copies the driver setup triage logs. |
| [IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents method](..\wppdefs\nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-waitnopendinginstallevents.md) | Waits until all device installations have completed. |
| [IWDTFEnhancedDeviceTestSupportAction2::Disable method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-disable.md) | Disables the Enhanced Device Test (EDT) filter driver on the target device. |
| [IWDTFEnhancedDeviceTestSupportAction2::Enable method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable.md) | Enables the Enhanced Device Test (EDT) filter driver on the target device. |
| [IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-isenabled.md) | Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device. |
| [IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-isrebootrequired.md) | Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot. |
| [IWDTFEnhancedDeviceTestSupportAction2::put_SkipRestart method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-put_skiprestart.md) | Sets a value that indicates whether the target device should be restarted by default. |
| [IWDTFEnhancedDeviceTestSupportActions2::Disable method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2-disable.md) | Disables the Enhanced Device Test (EDT) filter driver on the target device. |
| [IWDTFEnhancedDeviceTestSupportActions2::Enable method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2-enable.md) | Enables the Enhanced Device Test (EDT) filter driver on the target device. |
| [IWDTFEnhancedDeviceTestSupportActions2::IsEnabled method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2-isenabled.md) | Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device. |
| [IWDTFEnhancedDeviceTestSupportActions2::IsRebootRequired method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2-isrebootrequired.md) | Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot. |
| [IWDTFEnhancedDeviceTestSupportActions2::put_SkipRestart method](..\wppdefs\nf-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2-put_skiprestart.md) | Sets a value that indicates whether the target device should be restarted by default. |
| [IWDTFLOG2::EndTestCase method](..\wppdefs\nf-wdtf-iwdtflog2-endtestcase.md) | Marks the end of a test case. |
| [IWDTFLOG2::EndTestCase method](..\wppdefs\nf-wdtf-iwdtflog2-endtestcase.md) | Marks the end of a test case. |
| [IWDTFLOG2::OutputError method](..\wppdefs\nf-wdtf-iwdtflog2-outputerror.md) | Writes an error entry to the test case log. |
| [IWDTFLOG2::OutputError method](..\wppdefs\nf-wdtf-iwdtflog2-outputerror.md) | Writes an error entry to the test case log. |
| [IWDTFLOG2::OutputInfo method](..\wppdefs\nf-wdtf-iwdtflog2-outputinfo.md) | Writes an informational entry to the test case log. |
| [IWDTFLOG2::OutputInfo method](..\wppdefs\nf-wdtf-iwdtflog2-outputinfo.md) | Writes an informational entry to the test case log. |
| [IWDTFLOG2::StartTestCase method](..\wppdefs\nf-wdtf-iwdtflog2-starttestcase.md) | Marks the start of a test case. |
| [IWDTFLOG2::StartTestCase method](..\wppdefs\nf-wdtf-iwdtflog2-starttestcase.md) | Marks the start of a test case. |
| [IWDTFLongNumbers2::Add method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-add.md) | Adds a single long number to the collection. |
| [IWDTFLongNumbers2::Add method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-add.md) | Adds a single long number to the collection. |
| [IWDTFLongNumbers2::Remove method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-remove.md) | Removes a long number from the collection. |
| [IWDTFLongNumbers2::Remove method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-remove.md) | Removes a long number from the collection. |
| [IWDTFLongNumbers2::get_Count method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get_count.md) | Gets the number of long numbers in the collection. |
| [IWDTFLongNumbers2::get_Count method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get_count.md) | Gets the number of long numbers in the collection. |
| [IWDTFLongNumbers2::get_Item method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get_item.md) | Gets an individual long number in the collection. |
| [IWDTFLongNumbers2::get_Item method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get_item.md) | Gets an individual long number in the collection. |
| [IWDTFLongNumbers2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFLongNumbers2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtflongnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFNumbers2::Add method](..\wppdefs\nf-wdtf-iwdtfnumbers2-add.md) | Adds a single number to the collection. |
| [IWDTFNumbers2::Add method](..\wppdefs\nf-wdtf-iwdtfnumbers2-add.md) | Adds a single number to the collection. |
| [IWDTFNumbers2::Remove method](..\wppdefs\nf-wdtf-iwdtfnumbers2-remove.md) | Removes a number from the collection. |
| [IWDTFNumbers2::Remove method](..\wppdefs\nf-wdtf-iwdtfnumbers2-remove.md) | Removes a number from the collection. |
| [IWDTFNumbers2::get_Count method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get_count.md) | Gets the number of numbers in the collection. |
| [IWDTFNumbers2::get_Count method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get_count.md) | Gets the number of numbers in the collection. |
| [IWDTFNumbers2::get_Item method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get_item.md) | Gets an individual number in the collection. |
| [IWDTFNumbers2::get_Item method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get_item.md) | Gets an individual number in the collection. |
| [IWDTFNumbers2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFNumbers2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFPNPAction2::DisableDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-disabledevice.md) | Disables the target device. |
| [IWDTFPNPAction2::EDTCancelRemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edtcancelremovedevice.md) | Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTCancelStopDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edtcancelstopdevice.md) | Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTSurpriseRemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edtsurpriseremovedevice.md) | Sends an IRP_MN_SURPRISE_REMOVAL event to the target device. |
| [IWDTFPNPAction2::EDTTryStopDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevice.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTTryStopDeviceFailRestart method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicefailrestart.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart. |
| [IWDTFPNPAction2::EDTTryStopDeviceRequestNewResources method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicerequestnewresources.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and assign new resources to the target device. |
| [IWDTFPNPAction2::EnableDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-enabledevice.md) | Enables the target device. |
| [IWDTFPNPAction2::RemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-removedevice.md) | Removes the device. |
| [IWDTFPNPAction2::RequestEjectDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-requestejectdevice.md) | Initiates a device eject. |
| [IWDTFPNPAction2::RescanDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-rescandevice.md) | Rescans the target device. |
| [IWDTFPNPAction2::RescanParentDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-rescanparentdevice.md) | Rescans and re-enumerates the target device's parent device. |
| [IWDTFPNPAction2::RestartDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpaction2-restartdevice.md) | Initiates a device restart. |
| [IWDTFPNPActions2::DisableDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-disabledevice.md) | Disables the target device. |
| [IWDTFPNPActions2::EDTCancelRemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edtcancelremovedevice.md) | Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTCancelStopDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edtcancelstopdevice.md) | Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTSurpriseRemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edtsurpriseremovedevice.md) | Sends an IRP_MN_SURPRISE_REMOVAL event to the target device. |
| [IWDTFPNPActions2::EDTTryStopDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevice.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTTryStopDeviceFailRestart method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevicefailrestart.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart. |
| [IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevicerequestnewresources.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and assign new resources to the target device. |
| [IWDTFPNPActions2::EnableDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-enabledevice.md) | Enables the target device. |
| [IWDTFPNPActions2::RemoveDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-removedevice.md) | Removes the device. |
| [IWDTFPNPActions2::RequestEjectDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-requestejectdevice.md) | Initiates a device eject. |
| [IWDTFPNPActions2::RescanDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-rescandevice.md) | Rescans the target device. |
| [IWDTFPNPActions2::RescanParentDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-rescanparentdevice.md) | Rescans and re-enumerates the target device's parent device. |
| [IWDTFPNPActions2::RestartDevice method](..\wppdefs\nf-wdtfpnpaction-iwdtfpnpactions2-restartdevice.md) | Initiates a device restart. |
| [IWDTFSimpleIOEx2::Close method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleioex2-close.md) | Closes the device. |
| [IWDTFSimpleIOEx2::Open method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleioex2-open.md) | Opens the device. |
| [IWDTFSimpleIOEx2::PerformIO method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleioex2-performio.md) | Performs a small amount of simple I/O to the device. |
| [IWDTFSimpleIOStressAction2::Continue method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-continue.md) | Continues the I/O. |
| [IWDTFSimpleIOStressAction2::ContinueAsync method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-continueasync.md) | Asynchronously signals the I/O to continue. |
| [IWDTFSimpleIOStressAction2::Pause method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-pause.md) | Pauses the I/O. |
| [IWDTFSimpleIOStressAction2::Start method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-start.md) | Opens the device. |
| [IWDTFSimpleIOStressAction2::StartAsync method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-startasync.md) | Asynchronously signals a start event to occur. |
| [IWDTFSimpleIOStressAction2::Stop method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-stop.md) | Stops the device. |
| [IWDTFSimpleIOStressAction2::StopAsync method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-stopasync.md) | Asynchronously signals the stop event to occur. |
| [IWDTFSimpleIOStressAction2::WaitAsyncCompletion method](..\wppdefs\nf-wdtfinterfaces-iwdtfsimpleiostressaction2-waitasynccompletion.md) | Waits for the completion of any of the asynchronous events. |
| [IWDTFSimulatedBatterySystemAction::DisableRealBatteries method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-disablerealbatteries.md) | Disables real batteries if they are present in the system. |
| [IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-disablesimulatedbattery.md) | Disables the simulated battery. |
| [IWDTFSimulatedBatterySystemAction::EnableRealBatteries method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-enablerealbatteries.md) | Enables real batteries if they are present in the system. |
| [IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-enablesimulatedbattery.md) | Enables the simulated battery. |
| [IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-setsimulatedbatterychargepercentage.md) | Sets the charge percentage reported to the OS by the simulated battery. |
| [IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToAC method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-setsimulatedbatterytoac.md) | Sets the simulated battery status to AC power. |
| [IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC method](..\wppdefs\nf-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction-setsimulatedbatterytodc.md) | Sets the simulated battery status to DC power. |
| [IWDTFStrings2::Add method](..\wppdefs\nf-wdtf-iwdtfstrings2-add.md) | Adds a single string to the collection. |
| [IWDTFStrings2::Add method](..\wppdefs\nf-wdtf-iwdtfstrings2-add.md) | Adds a single string to the collection. |
| [IWDTFStrings2::Remove method](..\wppdefs\nf-wdtf-iwdtfstrings2-remove.md) | Removes a string from the collection. |
| [IWDTFStrings2::Remove method](..\wppdefs\nf-wdtf-iwdtfstrings2-remove.md) | Removes a string from the collection. |
| [IWDTFStrings2::get_Count method](..\wppdefs\nf-wdtf-iwdtfstrings2-get_count.md) | Gets the number of strings in the collection. |
| [IWDTFStrings2::get_Count method](..\wppdefs\nf-wdtf-iwdtfstrings2-get_count.md) | Gets the number of strings in the collection. |
| [IWDTFStrings2::get_Item method](..\wppdefs\nf-wdtf-iwdtfstrings2-get_item.md) | Gets an individual string in the collection. |
| [IWDTFStrings2::get_Item method](..\wppdefs\nf-wdtf-iwdtfstrings2-get_item.md) | Gets an individual string in the collection. |
| [IWDTFStrings2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfstrings2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFStrings2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtfstrings2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFSystemAction2::ConnectedStandby method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-connectedstandby.md) | Puts the system into Connected Standby state and exits Connected Standby state after the desired time has passed. This method only works on a computer that supports Always On Always Connected (AOAC). |
| [IWDTFSystemAction2::GetFirstSleepState method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-getfirstsleepstate.md) | Returns the first supported sleep state. |
| [IWDTFSystemAction2::GetNextSleepState method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-getnextsleepstate.md) | Returns the next supported sleep state. |
| [IWDTFSystemAction2::IsRestartedWithContext method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-isrestartedwithcontext.md) | Gets a value that indicates whether the test script was restarted for a specific context. |
| [IWDTFSystemAction2::PowerAnalyzeTraceByFile method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-poweranalyzetracebyfile.md) | Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. This method will only work on Windows 8 and above. |
| [IWDTFSystemAction2::PowerTracingEnd method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-powertracingend.md) | This method ends a power trace session. |
| [IWDTFSystemAction2::PowerTracingStart method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstart.md) | Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method is available starting with Windows 8. |
| [IWDTFSystemAction2::PowerTracingStartByFile method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstartbyfile.md) | Starts a trace session for power state transitions and saves the trace message file (.etl) using the specified path. This method is available starting with Windows 8. |
| [IWDTFSystemAction2::RebootRestart method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestart.md) | Restart the system and the current test. |
| [IWDTFSystemAction2::RebootRestartWithContext method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestartwithcontext.md) | Reboots the system and restarts the test script with context data. |
| [IWDTFSystemAction2::Sleep method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-sleep.md) | Puts the system into the desired sleep state. |
| [IWDTFSystemAction2::get_Critical method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-get_critical.md) | Gets or sets a value that indicates whether the the system power state is critical. |
| [IWDTFSystemAction2::get_IsRestarted method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-get_isrestarted.md) | Gets a value that indicates whether the test script restarted as a result of a call to RebootRestart or RebootRestartWithContext. |
| [IWDTFSystemAction2::get_SleepWakeTimeInSeconds method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-get_sleepwaketimeinseconds.md) | Gets or sets the time in seconds when the system will wake from the sleep state. |
| [IWDTFSystemAction2::put_Critical method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-put_critical.md) | Gets or sets a value that indicates whether the the system power state is critical. |
| [IWDTFSystemAction2::put_SleepWakeTimeInSeconds method](..\wppdefs\nf-wdtfsystemaction-iwdtfsystemaction2-put_sleepwaketimeinseconds.md) | Gets or sets the time in seconds when the system will wake from the sleep state. |
| [IWDTFSystemDepot2::get_ThisSystem method](..\wppdefs\nf-wdtf-iwdtfsystemdepot2-get_thissystem.md) | Gets an IWDTFTarget2 value that represents the local computer. |
| [IWDTFSystemDepot2::get_ThisSystem method](..\wppdefs\nf-wdtf-iwdtfsystemdepot2-get_thissystem.md) | Gets an IWDTFTarget2 value that represents the local computer. |
| [IWDTFSystemDepot2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtfsystemdepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFSystemDepot2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtfsystemdepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTarget2::Eval method](..\wppdefs\nf-wdtf-iwdtftarget2-eval.md) | Evaluate whether this target matches an SDEL statement. |
| [IWDTFTarget2::Eval method](..\wppdefs\nf-wdtf-iwdtftarget2-eval.md) | Evaluate whether this target matches an SDEL statement. |
| [IWDTFTarget2::GetInterface method](..\wppdefs\nf-wdtf-iwdtftarget2-getinterface.md) | Returns an action for the target. |
| [IWDTFTarget2::GetInterface method](..\wppdefs\nf-wdtf-iwdtftarget2-getinterface.md) | Returns an action for the target. |
| [IWDTFTarget2::GetRelations method](..\wppdefs\nf-wdtf-iwdtftarget2-getrelations.md) | Returns a collection of related targets. |
| [IWDTFTarget2::GetRelations method](..\wppdefs\nf-wdtf-iwdtftarget2-getrelations.md) | Returns a collection of related targets. |
| [IWDTFTarget2::GetValue method](..\wppdefs\nf-wdtf-iwdtftarget2-getvalue.md) | Returns a value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValue method](..\wppdefs\nf-wdtf-iwdtftarget2-getvalue.md) | Returns a value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueBool method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluebool.md) | Returns a boolean value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueBool method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluebool.md) | Returns a boolean value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumber method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluelongnumber.md) | Returns a long number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumber method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluelongnumber.md) | Returns a long number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumbers method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluelongnumbers.md) | Returns a collection of long number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumbers method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluelongnumbers.md) | Returns a collection of long number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumber method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluenumber.md) | Returns a number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumber method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluenumber.md) | Returns a number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumbers method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluenumbers.md) | Returns a collection of number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumbers method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluenumbers.md) | Returns a collection of number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueString method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluestring.md) | Returns a string value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueString method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluestring.md) | Returns a string value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueStrings method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluestrings.md) | Returns a collection of string values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueStrings method](..\wppdefs\nf-wdtf-iwdtftarget2-getvaluestrings.md) | Returns a collection of string values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::HasContext method](..\wppdefs\nf-wdtf-iwdtftarget2-hascontext.md) | Determines whether a given context exists for the target. |
| [IWDTFTarget2::HasContext method](..\wppdefs\nf-wdtf-iwdtftarget2-hascontext.md) | Determines whether a given context exists for the target. |
| [IWDTFTarget2::HasInterface method](..\wppdefs\nf-wdtf-iwdtftarget2-hasinterface.md) | Determines whether the target supports a given interface. |
| [IWDTFTarget2::HasInterface method](..\wppdefs\nf-wdtf-iwdtftarget2-hasinterface.md) | Determines whether the target supports a given interface. |
| [IWDTFTarget2::get_Context method](..\wppdefs\nf-wdtf-iwdtftarget2-get_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTarget2::get_Context method](..\wppdefs\nf-wdtf-iwdtftarget2-get_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTarget2::get_Type method](..\wppdefs\nf-wdtf-iwdtftarget2-get_type.md) | Gets a value that identifies the depot that the target comes from. |
| [IWDTFTarget2::get_Type method](..\wppdefs\nf-wdtf-iwdtftarget2-get_type.md) | Gets a value that identifies the depot that the target comes from. |
| [IWDTFTarget2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtftarget2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTarget2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtftarget2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTarget2::put_Context method](..\wppdefs\nf-wdtf-iwdtftarget2-put_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTarget2::put_Context method](..\wppdefs\nf-wdtf-iwdtftarget2-put_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTargets2::Add method](..\wppdefs\nf-wdtf-iwdtftargets2-add.md) | Add a single item to the collection. |
| [IWDTFTargets2::Add method](..\wppdefs\nf-wdtf-iwdtftargets2-add.md) | Add a single item to the collection. |
| [IWDTFTargets2::Clear method](..\wppdefs\nf-wdtf-iwdtftargets2-clear.md) | Removes all items from the collection. |
| [IWDTFTargets2::Clear method](..\wppdefs\nf-wdtf-iwdtftargets2-clear.md) | Removes all items from the collection. |
| [IWDTFTargets2::Eval method](..\wppdefs\nf-wdtf-iwdtftargets2-eval.md) | Evaluates whether all items in the collection match an SDEL statement. |
| [IWDTFTargets2::Eval method](..\wppdefs\nf-wdtf-iwdtftargets2-eval.md) | Evaluates whether all items in the collection match an SDEL statement. |
| [IWDTFTargets2::GetInterfaces method](..\wppdefs\nf-wdtf-iwdtftargets2-getinterfaces.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::GetInterfaces method](..\wppdefs\nf-wdtf-iwdtftargets2-getinterfaces.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::GetInterfacesIfExist method](..\wppdefs\nf-wdtf-iwdtftargets2-getinterfacesifexist.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::GetInterfacesIfExist method](..\wppdefs\nf-wdtf-iwdtftargets2-getinterfacesifexist.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::Query method](..\wppdefs\nf-wdtf-iwdtftargets2-query.md) | Returns a subset of the items in the collection. |
| [IWDTFTargets2::Query method](..\wppdefs\nf-wdtf-iwdtftargets2-query.md) | Returns a subset of the items in the collection. |
| [IWDTFTargets2::QuerySingle method](..\wppdefs\nf-wdtf-iwdtftargets2-querysingle.md) | Returns a single item from the collection. |
| [IWDTFTargets2::QuerySingle method](..\wppdefs\nf-wdtf-iwdtftargets2-querysingle.md) | Returns a single item from the collection. |
| [IWDTFTargets2::Remove method](..\wppdefs\nf-wdtf-iwdtftargets2-remove.md) | Removes an item from the collection. |
| [IWDTFTargets2::Remove method](..\wppdefs\nf-wdtf-iwdtftargets2-remove.md) | Removes an item from the collection. |
| [IWDTFTargets2::get_Count method](..\wppdefs\nf-wdtf-iwdtftargets2-get_count.md) | Gets the number of items in this collection. |
| [IWDTFTargets2::get_Count method](..\wppdefs\nf-wdtf-iwdtftargets2-get_count.md) | Gets the number of items in this collection. |
| [IWDTFTargets2::get_Item method](..\wppdefs\nf-wdtf-iwdtftargets2-get_item.md) | Gets an individual item in the collection. |
| [IWDTFTargets2::get_Item method](..\wppdefs\nf-wdtf-iwdtftargets2-get_item.md) | Gets an individual item in the collection. |
| [IWDTFTargets2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtftargets2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTargets2::get_WDTF method](..\wppdefs\nf-wdtf-iwdtftargets2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTargets2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtftargets2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFTargets2::get__NewEnum method](..\wppdefs\nf-wdtf-iwdtftargets2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
