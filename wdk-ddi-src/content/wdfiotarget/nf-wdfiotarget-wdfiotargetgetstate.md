---
UID: NF:wdfiotarget.WdfIoTargetGetState
title: WdfIoTargetGetState function
author: windows-driver-content
description: The WdfIoTargetGetState method returns state information for a local or remote I/O target.
old-location: wdf\wdfiotargetgetstate.htm
old-project: wdf
ms.assetid: 38e22922-d9de-4dfd-9da9-c131b789f5d6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoTargetGetState
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
req.alt-api: WdfIoTargetGetState
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetGetState function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetGetState</b> method returns state information for a local or remote I/O target.



## -syntax

````
WDF_IO_TARGET_STATE WdfIoTargetGetState(
  _In_ WDFIOTARGET IoTarget
);
````


## -parameters

### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


## -returns
<b>WdfIoTargetGetState</b> returns a <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_state.md">WDF_IO_TARGET_STATE</a>-typed value that indicates the state of the specified I/O target.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about <b>WdfIoTargetGetState</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

The following code example obtains state information for a USB I/O target.


## -see-also
<dl>
<dt>
<a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_state.md">WDF_IO_TARGET_STATE</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetGetState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

