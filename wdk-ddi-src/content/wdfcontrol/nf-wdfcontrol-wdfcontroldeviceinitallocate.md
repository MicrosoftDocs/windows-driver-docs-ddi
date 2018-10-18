---
UID: NF:wdfcontrol.WdfControlDeviceInitAllocate
title: WdfControlDeviceInitAllocate function
author: windows-driver-content
description: The WdfControlDeviceInitAllocate method allocates a WDFDEVICE_INIT structure that a driver uses when creating a new control device object.
old-location: wdf\wdfcontroldeviceinitallocate.htm
tech.root: wdf
ms.assetid: 3d423861-4c4d-45f2-bc44-b7cf1b230458
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectControllerDevObjRef_1450db30-6c2a-4103-99f6-2afe634000bf.xml, WdfControlDeviceInitAllocate, WdfControlDeviceInitAllocate method, kmdf.wdfcontroldeviceinitallocate, wdf.wdfcontroldeviceinitallocate, wdfcontrol/WdfControlDeviceInitAllocate
ms.topic: function
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ControlDeviceInitAPI, CtlDeviceFinishInitDeviceAdd, CtlDeviceFinishInitDrEntry, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeDeviceCreateType2, InitFreeDeviceCreateType4, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
-	WdfControlDeviceInitAllocate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfControlDeviceInitAllocate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfControlDeviceInitAllocate</b> method allocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that a driver uses when creating a new control device object.


## -parameters




### -param Driver [in]

A handle to a framework driver object.


### -param SDDLString [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that describes a Unicode string. This string is a Security Descriptor Definition Language (SDDL) representation of a security descriptor. For more information, see the following Remarks section.


## -returns



<b>WdfControlDeviceInitAllocate</b> returns a pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure, if the operation succeeds. Otherwise, the method returns <b>NULL</b>.




## -remarks



If you want your driver to create a control device object, the driver must call <b>WdfControlDeviceInitAllocate</b> to obtain a WDFDEVICE_INIT structure that it can pass to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. 

Your driver can specify a security setting by using a subset of SDDL. The <i>Wdmsec.h</i> file defines a set of SDDL_DEVOBJ_<i>Xxx</i>-formatted constants that you can use. For more information about security descriptors and SDDL, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563688">Securing Device Objects</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546035">WdfDeviceInitAssignSDDLString</a> method overwrites the security setting, if any, that <b>WdfControlDeviceInitAllocate</b> specifies.

For more information about calling <b>WdfControlDeviceInitAllocate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.


#### Examples

The following code example allocates a DEVICE_INIT structure, assigns a device object name, registers a shutdown notification callback function, and creates a control device object. For a more complex example that uses <b>WdfControlDeviceInitAllocate</b>, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample driver or the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NDISProt</a> sample driver.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PWDFDEVICE_INIT  deviceInit = NULL;
NTSTATUS  status;
WDF_OBJECT_ATTRIBUTES  objectAttribs;

deviceInit = WdfControlDeviceInitAllocate(
                                          hDriver,
                                          &amp;SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R
                                          );
if (deviceInit == NULL) {
    status = STATUS_INSUFFICIENT_RESOURCES;
    goto Error;
}
status = WdfDeviceInitAssignName(
                                 deviceInit,
                                 &amp;ntDeviceName
                                 );
if (!NT_SUCCESS(status)) {
    WdfDeviceInitFree(deviceInit);
    deviceInit = NULL;
    goto Error;
}
WdfControlDeviceInitSetShutdownNotification(
                                            deviceInit,
                                            EvtShutdownNotification,
                                            WdfDeviceShutdown
                                            );
WDF_OBJECT_ATTRIBUTES_INIT(&amp;objectAttribs);

status = WdfDeviceCreate(
                         &amp;deviceInit,
                         &amp;objectAttribs,
                         &amp;controlDevice
                         );
if (!NT_SUCCESS(status)) {
    WdfDeviceInitFree(deviceInit);
    deviceInit = NULL;
    goto Error;
}
WdfControlFinishInitializing(controlDevice);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545847">WdfControlDeviceInitSetShutdownNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545854">WdfControlFinishInitializing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546029">WdfDeviceInitAssignName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546035">WdfDeviceInitAssignSDDLString</a>
 

 

