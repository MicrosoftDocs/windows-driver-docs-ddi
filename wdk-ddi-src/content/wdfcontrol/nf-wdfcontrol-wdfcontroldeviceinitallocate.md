---
UID: NF:wdfcontrol.WdfControlDeviceInitAllocate
title: WdfControlDeviceInitAllocate function
author: windows-driver-content
description: The WdfControlDeviceInitAllocate method allocates a WDFDEVICE_INIT structure that a driver uses when creating a new control device object.
old-location: wdf\wdfcontroldeviceinitallocate.htm
old-project: wdf
ms.assetid: 3d423861-4c4d-45f2-bc44-b7cf1b230458
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfcontroldeviceinitallocate, PFN_WDFCONTROLDEVICEINITALLOCATE, DFDeviceObjectControllerDevObjRef_1450db30-6c2a-4103-99f6-2afe634000bf.xml, wdfcontrol/WdfControlDeviceInitAllocate, WdfControlDeviceInitAllocate, wdf.wdfcontroldeviceinitallocate, WdfControlDeviceInitAllocate method
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfControlDeviceInitAllocate
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# WdfControlDeviceInitAllocate function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfControlDeviceInitAllocate</b> method allocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that a driver uses when creating a new control device object.


## -syntax


````
PWDFDEVICE_INIT WdfControlDeviceInitAllocate(
  _In_       WDFDRIVER      Driver,
  _In_ const UNICODE_STRING *SDDLString
);
````


## -parameters




### -param Driver [in]

A handle to a framework driver object.


### -param SDDLString [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that describes a Unicode string. This string is a Security Descriptor Definition Language (SDDL) representation of a security descriptor. For more information, see the following Remarks section.


## -returns


<b>WdfControlDeviceInitAllocate</b> returns a pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure, if the operation succeeds. Otherwise, the method returns <b>NULL</b>.



## -remarks


If you want your driver to create a control device object, the driver must call <b>WdfControlDeviceInitAllocate</b> to obtain a WDFDEVICE_INIT structure that it can pass to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. 

Your driver can specify a security setting by using a subset of SDDL. The <i>Wdmsec.h</i> file defines a set of SDDL_DEVOBJ_<i>Xxx</i>-formatted constants that you can use. For more information about security descriptors and SDDL, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563688">Securing Device Objects</a>.

The <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a> method overwrites the security setting, if any, that <b>WdfControlDeviceInitAllocate</b> specifies.

For more information about calling <b>WdfControlDeviceInitAllocate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignname.md">WdfDeviceInitAssignName</a>

<a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification.md">WdfControlDeviceInitSetShutdownNotification</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

<a href="..\wdfcontrol\nf-wdfcontrol-wdfcontrolfinishinitializing.md">WdfControlFinishInitializing</a>

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfControlDeviceInitAllocate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

