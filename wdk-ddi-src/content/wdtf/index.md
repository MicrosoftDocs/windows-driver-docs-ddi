---
UID: NA:wdtf
ms.assetid: 14e419d2-ee55-3451-99ed-6d9c21181fb2
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtf.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtf.h contain these programming interfaces:


## Enumerations

| Title   | Description   |
| ---- |:---- |
| [__MIDL___MIDL_itf_wdtf_0000_0001_0001 enumeration](ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md) | The TTraceLevel enumeration defines a set of levels for tracing in WDTF. The meaning on each level depends on registry settings for the ITracer interface. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAction interface](nn-wdtf-iaction.md) | The IAction interfaces are plug-ins that can control an instance of the IWDTFTarget2 interface. |
| [ITracer interface](nn-wdtf-itracer.md) | The ITracer interface enables individual instances of every WDTF interface to determine the specific tracing settings for a given implementation coclass. These settings are recorded in the registry. |
| [ITracing interface](nn-wdtf-itracing.md) | The ITracing interface sets an object's TTraceLevel value. This interface is a base interface for most of the WDTF interfaces. |
| [IWDTF2 interface](nn-wdtf-iwdtf2.md) | Defines properties for the WDTF collection. |
| [IWDTFAction2 interface](nn-wdtf-iwdtfaction2.md) | Defines operations and properties that can control an instance of the IWDTFTarget2 interface. |
| [IWDTFActions2 interface](nn-wdtf-iwdtfactions2.md) | Defines operations and properties for the collection of actions that the IWDTFTargets |
| [IWDTFCONFIG2 interface](nn-wdtf-iwdtfconfig2.md) | Defines operations that control WDTF objects within a test script. |
| [IWDTFDeviceDepot2 interface](nn-wdtf-iwdtfdevicedepot2.md) | Defines properties and operations for the collection of devices on a computer. |
| [IWDTFLOG2 interface](nn-wdtf-iwdtflog2.md) | Defines operations that enable the test case author to add to the WDTF test log. |
| [IWDTFLongNumbers2 interface](nn-wdtf-iwdtflongnumbers2.md) | Defines operations and properties for a collection of long numbers. |
| [IWDTFNumbers2 interface](nn-wdtf-iwdtfnumbers2.md) | Defines operations and properties for a collection of numbers. |
| [IWDTFStrings2 interface](nn-wdtf-iwdtfstrings2.md) | Defines operations and properties for a collection of strings. |
| [IWDTFSystemDepot2 interface](nn-wdtf-iwdtfsystemdepot2.md) | Defines operations and properties for the SystemDepot - the object that represents the local computer. |
| [IWDTFTarget2 interface](nn-wdtf-iwdtftarget2.md) | Defines operations and properties for a testable item. |
| [IWDTFTargets2 interface](nn-wdtf-iwdtftargets2.md) | Defines properties and operations for the collection. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IAction::SetTarget method](nf-wdtf-iaction-settarget.md) | The SetTarget method is used internally by WDTF. Do not call this method directly. |
| [ITracer::GetBits method](nf-wdtf-itracer-getbits.md) | The GetBits method returns the set of tracing flags for a coclass as a bit mask, given a specified TTraceLevel value and the CLSID of the coclass. |
| [ITracing::SetTraceLevel method](nf-wdtf-itracing-settracelevel.md) | The SetTraceLevel method sets the tracing level for an object. |
| [IWDTF2::get_Config method](nf-wdtf-iwdtf2-get_config.md) | Gets the WDTF configuration object. |
| [IWDTF2::get_DeviceDepot method](nf-wdtf-iwdtf2-get_devicedepot.md) | Gets the DeviceDepot object. |
| [IWDTF2::get_Log method](nf-wdtf-iwdtf2-get_log.md) | Gets the WDTF log object. |
| [IWDTF2::get_SystemDepot method](nf-wdtf-iwdtf2-get_systemdepot.md) | Gets the SystemDepot object. |
| [IWDTFAction2::DisableObjectErrorLogging method](nf-wdtf-iwdtfaction2-disableobjecterrorlogging.md) | Disables object error logging for the action. |
| [IWDTFAction2::DisableObjectLogging method](nf-wdtf-iwdtfaction2-disableobjectlogging.md) | Disables object logging for the action. |
| [IWDTFAction2::EnableObjectErrorLogging method](nf-wdtf-iwdtfaction2-enableobjecterrorlogging.md) | Enables object error logging for the action. |
| [IWDTFAction2::EnableObjectLogging method](nf-wdtf-iwdtfaction2-enableobjectlogging.md) | Enables object logging for the action. |
| [IWDTFAction2::GetStatus method](nf-wdtf-iwdtfaction2-getstatus.md) | Returns the status code for the last operation. |
| [IWDTFAction2::GetStatusString method](nf-wdtf-iwdtfaction2-getstatusstring.md) | Returns the status for the last operation as a string. |
| [IWDTFAction2::IsStatusSuccess method](nf-wdtf-iwdtfaction2-isstatussuccess.md) | Gets a value that indicates whether the last operation was successful. |
| [IWDTFAction2::get_Target method](nf-wdtf-iwdtfaction2-get_target.md) | Gets the target to which this action refers. |
| [IWDTFActions2::Add method](nf-wdtf-iwdtfactions2-add.md) | Add a single action to the collection. |
| [IWDTFActions2::Clear method](nf-wdtf-iwdtfactions2-clear.md) | Removes all items from the collection. |
| [IWDTFActions2::DisableObjectErrorLogging method](nf-wdtf-iwdtfactions2-disableobjecterrorlogging.md) | Disable object error logging for all actions in the collection. |
| [IWDTFActions2::DisableObjectLogging method](nf-wdtf-iwdtfactions2-disableobjectlogging.md) | Disable object logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectErrorLogging method](nf-wdtf-iwdtfactions2-enableobjecterrorlogging.md) | Enable object error logging for all actions in the collection. |
| [IWDTFActions2::EnableObjectLogging method](nf-wdtf-iwdtfactions2-enableobjectlogging.md) | Enable object logging for all actions in the collection. |
| [IWDTFActions2::Remove method](nf-wdtf-iwdtfactions2-remove.md) | Remove an action from the collection. |
| [IWDTFActions2::get_Count method](nf-wdtf-iwdtfactions2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFActions2::get_Item method](nf-wdtf-iwdtfactions2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFActions2::get__NewEnum method](nf-wdtf-iwdtfactions2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFCONFIG2::DisableObjectErrorLogging method](nf-wdtf-iwdtfconfig2-disableobjecterrorlogging.md) | Disables object error logging for all objects. |
| [IWDTFCONFIG2::DisableObjectLogging method](nf-wdtf-iwdtfconfig2-disableobjectlogging.md) | Disables object logging for all objects. |
| [IWDTFCONFIG2::EnableObjectErrorLogging method](nf-wdtf-iwdtfconfig2-enableobjecterrorlogging.md) | Enables object error logging for all objects. |
| [IWDTFCONFIG2::EnableObjectLogging method](nf-wdtf-iwdtfconfig2-enableobjectlogging.md) | Enables object logging for all objects. |
| [IWDTFDeviceDepot2::Query method](nf-wdtf-iwdtfdevicedepot2-query.md) | Returns a subset of the devices in the DeviceDepot. |
| [IWDTFDeviceDepot2::QuerySingle method](nf-wdtf-iwdtfdevicedepot2-querysingle.md) | Returns a single target device from the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Count method](nf-wdtf-iwdtfdevicedepot2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFDeviceDepot2::get_Item method](nf-wdtf-iwdtfdevicedepot2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFDeviceDepot2::get_RootDevice method](nf-wdtf-iwdtfdevicedepot2-get_rootdevice.md) | Gets the root device. |
| [IWDTFDeviceDepot2::get_WDTF method](nf-wdtf-iwdtfdevicedepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFDeviceDepot2::get__NewEnum method](nf-wdtf-iwdtfdevicedepot2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFLOG2::EndTestCase method](nf-wdtf-iwdtflog2-endtestcase.md) | Marks the end of a test case. |
| [IWDTFLOG2::OutputError method](nf-wdtf-iwdtflog2-outputerror.md) | Writes an error entry to the test case log. |
| [IWDTFLOG2::OutputInfo method](nf-wdtf-iwdtflog2-outputinfo.md) | Writes an informational entry to the test case log. |
| [IWDTFLOG2::StartTestCase method](nf-wdtf-iwdtflog2-starttestcase.md) | Marks the start of a test case. |
| [IWDTFLongNumbers2::Add method](nf-wdtf-iwdtflongnumbers2-add.md) | Adds a single long number to the collection. |
| [IWDTFLongNumbers2::Remove method](nf-wdtf-iwdtflongnumbers2-remove.md) | Removes a long number from the collection. |
| [IWDTFLongNumbers2::get_Count method](nf-wdtf-iwdtflongnumbers2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFLongNumbers2::get_Item method](nf-wdtf-iwdtflongnumbers2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFLongNumbers2::get__NewEnum method](nf-wdtf-iwdtflongnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFNumbers2::Add method](nf-wdtf-iwdtfnumbers2-add.md) | Adds a single number to the collection. |
| [IWDTFNumbers2::Remove method](nf-wdtf-iwdtfnumbers2-remove.md) | Removes a number from the collection. |
| [IWDTFNumbers2::get_Count method](nf-wdtf-iwdtfnumbers2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFNumbers2::get_Item method](nf-wdtf-iwdtfnumbers2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFNumbers2::get__NewEnum method](nf-wdtf-iwdtfnumbers2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFStrings2::Add method](nf-wdtf-iwdtfstrings2-add.md) | Adds a single string to the collection. |
| [IWDTFStrings2::Remove method](nf-wdtf-iwdtfstrings2-remove.md) | Removes a string from the collection. |
| [IWDTFStrings2::get_Count method](nf-wdtf-iwdtfstrings2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFStrings2::get_Item method](nf-wdtf-iwdtfstrings2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFStrings2::get__NewEnum method](nf-wdtf-iwdtfstrings2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
| [IWDTFSystemDepot2::get_ThisSystem method](nf-wdtf-iwdtfsystemdepot2-get_thissystem.md) | Gets an IWDTFTarget2 value that represents the local computer. |
| [IWDTFSystemDepot2::get_WDTF method](nf-wdtf-iwdtfsystemdepot2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTarget2::Eval method](nf-wdtf-iwdtftarget2-eval.md) | Evaluate whether this target matches an SDEL statement. |
| [IWDTFTarget2::GetInterface method](nf-wdtf-iwdtftarget2-getinterface.md) | Returns an action for the target. |
| [IWDTFTarget2::GetRelations method](nf-wdtf-iwdtftarget2-getrelations.md) | Returns a collection of related targets. |
| [IWDTFTarget2::GetValue method](nf-wdtf-iwdtftarget2-getvalue.md) | Returns a value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueBool method](nf-wdtf-iwdtftarget2-getvaluebool.md) | Returns a boolean value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumber method](nf-wdtf-iwdtftarget2-getvaluelongnumber.md) | Returns a long number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueLongNumbers method](nf-wdtf-iwdtftarget2-getvaluelongnumbers.md) | Returns a collection of long number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumber method](nf-wdtf-iwdtftarget2-getvaluenumber.md) | Returns a number value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueNumbers method](nf-wdtf-iwdtftarget2-getvaluenumbers.md) | Returns a collection of number values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::GetValueString method](nf-wdtf-iwdtftarget2-getvaluestring.md) | Returns a string value from the target that is associated with a specified attribute. |
| [IWDTFTarget2::GetValueStrings method](nf-wdtf-iwdtftarget2-getvaluestrings.md) | Returns a collection of string values from the target that are associated with a specified attribute. |
| [IWDTFTarget2::HasContext method](nf-wdtf-iwdtftarget2-hascontext.md) | Determines whether a given context exists for the target. |
| [IWDTFTarget2::HasInterface method](nf-wdtf-iwdtftarget2-hasinterface.md) | Determines whether the target supports a given interface. |
| [IWDTFTarget2::get_Context method](nf-wdtf-iwdtftarget2-get_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTarget2::get_Type method](nf-wdtf-iwdtftarget2-get_type.md) | Gets a value that identifies the depot that the target comes from. |
| [IWDTFTarget2::get_WDTF method](nf-wdtf-iwdtftarget2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTarget2::put_Context method](nf-wdtf-iwdtftarget2-put_context.md) | Gets and sets a name-value pair that represents user data for the target. |
| [IWDTFTargets2::Add method](nf-wdtf-iwdtftargets2-add.md) | Add a single item to the collection. |
| [IWDTFTargets2::Clear method](nf-wdtf-iwdtftargets2-clear.md) | Removes all items from the collection. |
| [IWDTFTargets2::Eval method](nf-wdtf-iwdtftargets2-eval.md) | Evaluates whether all items in the collection match an SDEL statement. |
| [IWDTFTargets2::GetInterfaces method](nf-wdtf-iwdtftargets2-getinterfaces.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::GetInterfacesIfExist method](nf-wdtf-iwdtftargets2-getinterfacesifexist.md) | Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one. |
| [IWDTFTargets2::Query method](nf-wdtf-iwdtftargets2-query.md) | Returns a subset of the items in the collection. |
| [IWDTFTargets2::QuerySingle method](nf-wdtf-iwdtftargets2-querysingle.md) | Returns a single item from the collection. |
| [IWDTFTargets2::Remove method](nf-wdtf-iwdtftargets2-remove.md) | Removes an item from the collection. |
| [IWDTFTargets2::get_Count method](nf-wdtf-iwdtftargets2-get_count.md) | Gets the number of devices that are currently provided by the DeviceDepot. |
| [IWDTFTargets2::get_Item method](nf-wdtf-iwdtftargets2-get_item.md) | Gets an individual device in the DeviceDepot. |
| [IWDTFTargets2::get_WDTF method](nf-wdtf-iwdtftargets2-get_wdtf.md) | Gets the main WDTF aggregation object. |
| [IWDTFTargets2::get__NewEnum method](nf-wdtf-iwdtftargets2-get__newenum.md) | Gets a new iteration variable that the For Each loop structure implicitly uses. |
