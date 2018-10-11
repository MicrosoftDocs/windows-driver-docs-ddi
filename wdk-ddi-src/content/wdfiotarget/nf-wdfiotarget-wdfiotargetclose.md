---
UID: NF:wdfiotarget.WdfIoTargetClose
title: WdfIoTargetClose function
author: windows-driver-content
description: The WdfIoTargetClose method closes a specified remote I/O target.
old-location: wdf\wdfiotargetclose.htm
tech.root: wdf
ms.assetid: 7de1ce11-a2b3-4d68-b279-4652b822297b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_3ef7f2b7-6919-46d7-b48c-10dc135905d4.xml, WdfIoTargetClose, WdfIoTargetClose method, kmdf.wdfiotargetclose, wdf.wdfiotargetclose, wdfiotarget/WdfIoTargetClose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
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
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
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
-	WdfIoTargetClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetClose function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetClose</b> method closes a specified remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver has called <b>WdfIoTargetClose</b>, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a> to reopen the remote I/O target.

Drivers that supply an <a href="https://msdn.microsoft.com/204f101d-770c-4363-9371-0ee76dfa0b2c">EvtIoTargetRemoveComplete</a> callback function must call <b>WdfIoTargetClose</b> from within that callback function.

Before the <b>WdfIoTargetClose</b> method returns, the framework <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all of the target queue's I/O requests. 

If a driver has finished using a remote I/O target and will not use the target again, and the target has no child request objects that are still pending, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> without first calling <b>WdfIoTargetClose</b>. The call to <b>WdfObjectDelete</b> will close the remote I/O target, cancel all of the target queue's I/O requests, and delete the I/O target object. (Note that if the remote I/O target's parent object is a device object, the framework closes the target and deletes the target object when it deletes the parent object.) If the target has any child request objects that are still pending, the driver must call <b>WdfIoTargetClose</b> before it can safely call <b>WdfObjectDelete</b>.

For more information about <b>WdfIoTargetClose</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example is an <a href="https://msdn.microsoft.com/204f101d-770c-4363-9371-0ee76dfa0b2c">EvtIoTargetRemoveComplete</a> callback function that removes a specified I/O target from a driver's collection of I/O targets and then closes the I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoTargetRemoveComplete(
    WDFIOTARGET IoTarget
)
{
    //
    // Get device information from the I/O target object's
    // context space.
    //
    targetDeviceInfo = GetTargetDeviceInfo(IoTarget);
    deviceExtension = targetDeviceInfo-&gt;DeviceExtension;

    //
    // Remove the target device from the collection.
    //
    WdfWaitLockAcquire(
                       deviceExtension-&gt;TargetDeviceCollectionLock,
                       NULL
                       );

    WdfCollectionRemove(
                        deviceExtension-&gt;TargetDeviceCollection,
                        IoTarget
                        );

    WdfWaitLockRelease(deviceExtension-&gt;TargetDeviceCollectionLock);

    //
    // Close the target.
    //
    WdfIoTargetClose(IoTarget);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/204f101d-770c-4363-9371-0ee76dfa0b2c">EvtIoTargetRemoveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>
 

 

