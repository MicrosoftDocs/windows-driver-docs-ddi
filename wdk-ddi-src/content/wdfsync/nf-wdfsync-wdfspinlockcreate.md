---
UID: NF:wdfsync.WdfSpinLockCreate
title: WdfSpinLockCreate function
author: windows-driver-content
description: The WdfSpinLockCreate method creates a framework spin-lock object.
old-location: wdf\wdfspinlockcreate.htm
old-project: wdf
ms.assetid: 2854fa05-61a9-4515-9dc1-463f160ae89a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, DFSynchroRef_6e5f9884-82a8-4c1e-a039-9e01f4f3d0f1.xml, L, S, W, WdfSpinLockCreate, WdfSpinLockCreate method, a, c, d, e, f, i, k, kmdf.wdfspinlockcreate, n, o, p, r, t, wdf.wdfspinlockcreate, wdfsync/WdfSpinLockCreate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfSpinLockCreate
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfSpinLockCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfSpinLockCreate</b> method creates a framework spin-lock object.


## -syntax


````
NTSTATUS WdfSpinLockCreate(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES SpinLockAttributes,
  _Out_    WDFSPINLOCK            *SpinLock
);
````


## -parameters




### -param SpinLockAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the spin-lock object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param SpinLock [out]

A pointer to a location that receives a handle to a new framework spin-lock object.


## -returns



<b>WdfSpinLockCreate</b> returns STATUS_SUCCESS if the operation succeeds. 

For a list of other return values that the <b>WdfSpinLockCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfSpinLockCreate</b> method creates a framework spin-lock object. After creating a spin-lock object, a driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550040">WdfSpinLockAcquire</a> to acquire the lock and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550044">WdfSpinLockRelease</a> to release the lock.

By default, the new spin-lock object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the spin-lock object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the spin-lock object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about spin locks, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>, specifies that the spin lock's parent object will be a device object, and calls <b>WdfSpinLockCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES attributes;
WDFSPINLOCK lockHandle;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = Device;
status = WdfSpinLockCreate(
                           &amp;attributes,
                           &amp;lockHandle
                           );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550044">WdfSpinLockRelease</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550040">WdfSpinLockAcquire</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfSpinLockCreate method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

