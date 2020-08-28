---
UID: NF:wdfsync.WdfSpinLockCreate
title: WdfSpinLockCreate function (wdfsync.h)
description: The WdfSpinLockCreate method creates a framework spin-lock object.
old-location: wdf\wdfspinlockcreate.htm
tech.root: wdf
ms.assetid: 2854fa05-61a9-4515-9dc1-463f160ae89a
ms.date: 02/26/2018
keywords: ["WdfSpinLockCreate function"]
ms.keywords: DFSynchroRef_6e5f9884-82a8-4c1e-a039-9e01f4f3d0f1.xml, WdfSpinLockCreate, WdfSpinLockCreate method, kmdf.wdfspinlockcreate, wdf.wdfspinlockcreate, wdfsync/WdfSpinLockCreate
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ParentObjectCheckLock, WdfSpinlock
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfSpinLockCreate
 - wdfsync/WdfSpinLockCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfSpinLockCreate
---

# WdfSpinLockCreate function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfSpinLockCreate</b> method creates a framework spin-lock object.

## -parameters

### -param SpinLockAttributes 

[in, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the spin-lock object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param SpinLock 

[out]
A pointer to a location that receives a handle to a new framework spin-lock object.

## -returns

<b>WdfSpinLockCreate</b> returns STATUS_SUCCESS if the operation succeeds. 

For a list of other return values that the <b>WdfSpinLockCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>WdfSpinLockCreate</b> method creates a framework spin-lock object. After creating a spin-lock object, a driver can call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550040(v=vs.85)">WdfSpinLockAcquire</a> to acquire the lock and <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550044(v=vs.85)">WdfSpinLockRelease</a> to release the lock.

By default, the new spin-lock object's parent is the framework driver object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the spin-lock object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the spin-lock object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>, specifies that the spin lock's parent object will be a device object, and calls <b>WdfSpinLockCreate</b>.

```cpp
WDF_OBJECT_ATTRIBUTES attributes;
WDFSPINLOCK lockHandle;

WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
attributes.ParentObject = Device;
status = WdfSpinLockCreate(
                           &attributes,
                           &lockHandle
                           );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550040(v=vs.85)">WdfSpinLockAcquire</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550044(v=vs.85)">WdfSpinLockRelease</a>

