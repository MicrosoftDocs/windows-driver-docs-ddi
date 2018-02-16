---
UID: NC:wdfsync.PFN_WDFOBJECTACQUIRELOCK
title: PFN_WDFOBJECTACQUIRELOCK
author: windows-driver-content
description: The WdfObjectAcquireLock method acquires an object's synchronization lock.
old-location: wdf\wdfobjectacquirelock.htm
old-project: wdf
ms.assetid: 9a6aca10-f0b2-4476-93c7-b3670d239b15
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfobjectacquirelock, PFN_WDFOBJECTACQUIRELOCK, WdfObjectAcquireLock callback function, WdfObjectAcquireLock, wdfsync/WdfObjectAcquireLock, DFSynchroRef_d6a841c3-cbcb-4072-861a-5666dc2b4b02.xml, kmdf.wdfobjectacquirelock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdfsync.h
apiname:
-	WdfObjectAcquireLock
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---

# PFN_WDFOBJECTACQUIRELOCK callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectAcquireLock</b> method acquires an object's synchronization lock.


## -prototype


````
VOID WdfObjectAcquireLock(
  _In_ WDFOBJECT Object
);
````


## -parameters




### -param DriverGlobals



### -param WDFOBJECT






#### - Object [in]

A handle to a framework device object or a framework queue object.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


A driver can call the <b>WdfObjectAcquireLock</b> method to acquire the synchronization lock that is associated with a specified framework device object or framework queue object. The method does not return until the lock has been acquired.

When the driver no longer needs the object's synchronization lock, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548765">WdfObjectReleaseLock</a>.

If the driver specified <b>WdfExecutionLevelPassive</b> for the <b>ExecutionLevel</b> member of the specified object's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, the driver must call <b>WdfObjectAcquireLock</b> at IRQL &lt;= APC_LEVEL. <b>WdfObjectAcquireLock</b> acquires a <a href="https://msdn.microsoft.com/8c8014bf-6b81-4039-ae93-d4cedd6d6fed">fast mutex</a> and returns at the caller's IRQL. (In this case, <b>WdfObjectAcquireLock</b> also calls <a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a> before returning so that <a href="https://msdn.microsoft.com/74ed953c-1b2a-40b9-9df3-16869b198b38">normal kernel APCs</a> are disabled.)

If the driver did <i>not</i> specify <b>WdfExecutionLevelPassive</b> for the <b>ExecutionLevel</b> member of the specified object's WDF_OBJECT_ATTRIBUTES structure, the driver must call <b>WdfObjectAcquireLock</b> at IRQL &lt;= DISPATCH_LEVEL. <b>WdfObjectAcquireLock</b> acquires a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> and returns at IRQL = DISPATCH_LEVEL. 

For more information about synchronization locks, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548765">WdfObjectReleaseLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectAcquireLock callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

