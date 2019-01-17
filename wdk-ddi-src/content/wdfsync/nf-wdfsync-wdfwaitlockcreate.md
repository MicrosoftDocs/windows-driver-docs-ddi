---
UID: NF:wdfsync.WdfWaitLockCreate
title: WdfWaitLockCreate function
description: The WdfWaitLockCreate method creates a framework wait-lock object.
old-location: wdf\wdfwaitlockcreate.htm
tech.root: wdf
ms.assetid: a0ffa493-4490-440b-9f67-426a7b5d4442
ms.date: 02/26/2018
ms.keywords: DFSynchroRef_19d02cf5-4fa3-449c-8913-4a5ff80bd578.xml, WdfWaitLockCreate, WdfWaitLockCreate method, kmdf.wdfwaitlockcreate, wdf.wdfwaitlockcreate, wdfsync/WdfWaitLockCreate
ms.topic: function
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ParentObjectCheckLock
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfWaitLockCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWaitLockCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWaitLockCreate</b> method creates a framework wait-lock object.


## -parameters




### -param LockAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the wait-lock object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Lock [out]

A pointer to a location that receives a handle to a new framework wait-lock object.


## -returns



<b>WdfWaitLockCreate</b> returns STATUS_SUCCESS if the operation succeeds. 

For a list of other return values that the <b>WdfWaitLockCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfWaitLockCreate</b> method creates a framework wait-lock object. After creating a wait-lock object, a driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a> to acquire the lock and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556116">WdfWaitLockRelease</a> to release the lock.

By default, the new wait-lock object's parent is the framework driver object that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the wait-lock object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the wait-lock object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about wait locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>, specifies that the wait lock's parent object will be a device object, and calls <b>WdfWaitLockCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES attributes;
WDFWAITLOCK lockHandle;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = Device;
status = WdfWaitLockCreate(
                           &amp;attributes,
                           &amp;lockHandle
                           );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556116">WdfWaitLockRelease</a>
 

 

