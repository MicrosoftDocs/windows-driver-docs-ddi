---
UID: NF:wdfiotarget.WdfIoTargetGetDevice
title: WdfIoTargetGetDevice function (wdfiotarget.h)
description: The WdfIoTargetGetDevice method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.
old-location: wdf\wdfiotargetgetdevice.htm
tech.root: wdf
ms.assetid: 2e076f2f-59e3-43ca-b83e-3079bbf41df3
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_796e5254-23b4-4ed1-b02b-66c5c8560769.xml, WdfIoTargetGetDevice, WdfIoTargetGetDevice method, kmdf.wdfiotargetgetdevice, wdf.wdfiotargetgetdevice, wdfiotarget/WdfIoTargetGetDevice
ms.topic: function
f1_keywords:
 - "wdfiotarget/WdfIoTargetGetDevice"
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
req.irql: <=DISPATCH_LEVEL
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
- WdfIoTargetGetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetGetDevice</b> method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. This handle is obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method that a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/introduction-to-i-o-targets">specialized I/O target</a> supplies (such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetiotarget">WdfUsbTargetDeviceGetIoTarget</a>).


## -returns



<b>WdfIoTargetGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about <b>WdfIoTargetGetDevice</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example is shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function can call <b>WdfIoTargetGetDevice</b>.

```cpp
NTSTATUS
MyEvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
WDFDEVICE device;
...
device = WdfIoTargetGetDevice(IoTarget);
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetiotarget">WdfUsbTargetDeviceGetIoTarget</a>
 

 

