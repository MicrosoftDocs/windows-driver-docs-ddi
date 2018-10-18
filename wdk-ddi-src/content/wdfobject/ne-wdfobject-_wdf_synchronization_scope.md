---
UID: NE:wdfobject._WDF_SYNCHRONIZATION_SCOPE
title: "_WDF_SYNCHRONIZATION_SCOPE"
author: windows-driver-content
description: The WDF_SYNCHRONIZATION_SCOPE enumeration type specifies how the framework will synchronize execution of an object's event callback functions.
old-location: wdf\wdf_synchronization_scope.htm
tech.root: wdf
ms.assetid: a251bf5c-c09b-4097-a9ed-82f2312ac408
ms.date: 2/26/2018
ms.keywords: DFGenObjectRef_62dd47ff-1d2a-454e-9083-cbf68f1679d2.xml, WDF_SYNCHRONIZATION_SCOPE, WDF_SYNCHRONIZATION_SCOPE enumeration, WdfSynchronizationScopeDevice, WdfSynchronizationScopeInheritFromParent, WdfSynchronizationScopeInvalid, WdfSynchronizationScopeNone, WdfSynchronizationScopeQueue, _WDF_SYNCHRONIZATION_SCOPE, kmdf.wdf_synchronization_scope, wdf.wdf_synchronization_scope, wdfobject/WDF_SYNCHRONIZATION_SCOPE, wdfobject/WdfSynchronizationScopeDevice, wdfobject/WdfSynchronizationScopeInheritFromParent, wdfobject/WdfSynchronizationScopeInvalid, wdfobject/WdfSynchronizationScopeNone, wdfobject/WdfSynchronizationScopeQueue
ms.topic: enum
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfobject.h
api_name:
-	WDF_SYNCHRONIZATION_SCOPE
product:
- Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
---

# _WDF_SYNCHRONIZATION_SCOPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The WDF_SYNCHRONIZATION_SCOPE enumeration type specifies how the framework will synchronize execution of an object's event callback functions.


## -enum-fields




### -field WdfSynchronizationScopeInvalid

Reserved for system use.


### -field WdfSynchronizationScopeInheritFromParent

The framework uses the synchronization scope value that was specified for the object's parent object. This value is the default if a driver does not specify a WDF_SYNCHRONIZATION_SCOPE-typed value.


### -field WdfSynchronizationScopeDevice

The framework synchronizes execution of the event callback functions of all queue and file objects that are underneath a device object in the driver's object hierarchy. 

Additionally, if the driver sets the <b>AutomaticSerialization</b> member to <b>TRUE</b> in the configuration structure for an interrupt, DPC, work-item, or timer object that is underneath the same device object, the framework also synchronizes that object's callback functions. 

The framework obtains the device object's synchronization lock before calling a callback function. Therefore, these callback functions run one at a time. However, if the driver creates multiple objects of the same type, but under different device objects, their event callback functions might run concurrently on a multiprocessor system.


### -field WdfSynchronizationScopeQueue

This value affects queue objects only. The framework synchronizes the event callback functions of the queue object so that only one executes at a time. 

Additionally, if the driver sets <b>AutomaticSerialization</b> to <b>TRUE</b> in the configuration structure for an interrupt, DPC, work-item, or timer object that is underneath the queue object or its parent device object, the framework also synchronizes that object's callback functions. 

The framework obtains the queue object's synchronization lock before calling any callback functions that belong to the object. 

If the driver creates multiple queue objects, their event callback functions might run concurrently on a multiprocessor system.

For framework versions 1.9 and later, a driver should set <b>WdfSynchronizationScopeQueue</b> for individual queue objects. To use this scope with earlier versions of the framework, the driver must set <b>WdfSynchronizationScopeQueue</b> for the parent device object and <b>WdfSynchronizationScopeInheritFromParent</b> for the queue object.


### -field WdfSynchronizationScopeNone

The framework does not synchronize the object's event callback functions, so the callback functions might run concurrently on a multiprocessor system.


## -remarks



Drivers use the WDF_SYNCHRONIZATION_SCOPE enumeration type to specify the <b>SynchronizationScope</b> member of an object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure.

You can specify a <b>SynchronizationScope</b> value for only the following objects:

<ul>
<li>
Framework driver objects

</li>
<li>
Framework device objects

</li>
<li>
Framework queue objects

</li>
</ul>
The framework sets the <b>SynchronizationScope</b> value of framework driver objects to <b>WdfSynchronizationScopeNone</b>. It sets the <b>SynchronizationScope</b> value of framework device objects and framework queue objects to <b>WdfSynchronizationScopeInheritFromParent</b>.

For more information about synchronization of a driver's event callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>
 

 

