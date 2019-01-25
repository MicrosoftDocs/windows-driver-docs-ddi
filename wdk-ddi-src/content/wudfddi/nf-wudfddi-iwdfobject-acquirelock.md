---
UID: NF:wudfddi.IWDFObject.AcquireLock
title: IWDFObject::AcquireLock (wudfddi.h)
description: The AcquireLock method prevents the framework from calling methods of interfaces that a driver registered.
old-location: wdf\iwdfobject_acquirelock.htm
tech.root: wdf
ms.assetid: f69328fb-356b-4381-ae6e-df39ac60e032
ms.date: 02/26/2018
ms.keywords: AcquireLock, AcquireLock method, AcquireLock method,IWDFObject interface, IWDFObject interface,AcquireLock method, IWDFObject.AcquireLock, IWDFObject::AcquireLock, UMDFBaseObjectRef_3a9b581b-87cd-489d-b945-924489d5c3b9.xml, umdf.iwdfobject_acquirelock, wdf.iwdfobject_acquirelock, wudfddi/IWDFObject::AcquireLock
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFObject.AcquireLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFObject::AcquireLock


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AcquireLock</b> method prevents the framework from calling methods of interfaces that a driver registered.


## -parameters






## -returns



None




## -remarks



If a driver configured itself to use the <b>AcquireLock</b> locking scheme, the framework automatically acquires the "presentation" lock before calling into the driver. (For more information about this locking scheme, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-a-callback-synchronization-mode">Specifying a Callback Synchronization Mode</a>.) The <b>AcquireLock</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560214">IWDFObject::ReleaseLock</a> methods acquire and release the presentation lock, respectively. <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Framework device objects</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-i-o-queue-object">framework I/O queue objects</a> currently support the <b>AcquireLock</b> method.

The driver calls the <b>AcquireLock</b> method to manipulate its objects that were created from its callback interfaces outside the callback scope in a thread-safe manner. The <b>AcquireLock</b> method represents an advanced feature of the framework that most drivers will not use because improper usage can result in deadlocks.

Unsynchronized code can call <b>AcquireLock</b>. The driver should call on objects that match its synchronization scope.


#### Examples

For a code example of how to use the <b>AcquireLock</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560214">IWDFObject::ReleaseLock</a>
 

 

