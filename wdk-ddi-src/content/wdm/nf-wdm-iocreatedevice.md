---
UID: NF:wdm.IoCreateDevice
title: IoCreateDevice function
author: windows-driver-content
description: The IoCreateDevice routine creates a device object for use by a driver.
old-location: kernel\iocreatedevice.htm
old-project: kernel
ms.assetid: 54ca9dc8-8095-4b62-9ebc-f297abb429ca
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/IoCreateDevice, k104_1e38a631-7e65-4b4b-8d51-3150a8073511.xml, IoCreateDevice routine [Kernel-Mode Driver Architecture], kernel.iocreatedevice, IoCreateDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: AddDevice, CheckDeviceObjectFlags, IrqlIoPassive1, MiniportOnlyWdmDevice, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCreateDevice
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCreateDevice function


## -description


The <b>IoCreateDevice</b> routine creates a device object for use by a driver.


## -syntax


````
NTSTATUS IoCreateDevice(
  _In_     PDRIVER_OBJECT  DriverObject,
  _In_     ULONG           DeviceExtensionSize,
  _In_opt_ PUNICODE_STRING DeviceName,
  _In_     DEVICE_TYPE     DeviceType,
  _In_     ULONG           DeviceCharacteristics,
  _In_     BOOLEAN         Exclusive,
  _Out_    PDEVICE_OBJECT  *DeviceObject
);
````


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the caller. Each driver receives a pointer to its driver object in a parameter to its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. WDM function and filter drivers also receive a driver object pointer in their <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routines.


### -param DeviceExtensionSize [in]

Specifies the driver-determined number of bytes to be allocated for the <a href="https://msdn.microsoft.com/9ea59994-1112-4ae5-96a8-fa0670694b53">device extension</a> of the device object. The internal structure of the device extension is driver-defined.


### -param DeviceName [in, optional]

Optionally points to a buffer containing a null-terminated Unicode string that names the device object. The string must be a full path name. WDM filter and function drivers do not name their device objects. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556420">Named Device Objects</a>.
     

<div class="alert"><b>Note</b>  If a device name is not supplied (that is, <i>DeviceName</i> is <b>NULL</b>), the device object created by <b>IoCreateDevice</b> will not (and cannot) have a discretionary access control list (DACL) associated with it. For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563698">Security Descriptors</a>.</div>
<div> </div>

### -param DeviceType [in]

Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants that indicate the type of device (such as FILE_DEVICE_DISK or FILE_DEVICE_KEYBOARD) or a vendor-defined value for a new type of device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.


### -param DeviceCharacteristics [in]

Specifies one or more system-defined constants, ORed together, that provide additional information about the driver's device. For a list of possible device characteristics, see <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>. For more information about how to specify device characteristics, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563818">Specifying Device Characteristics</a>. Most drivers specify FILE_DEVICE_SECURE_OPEN for this parameter.


### -param Exclusive [in]

Specifies if the device object represents an <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exclusive device</a>. Most drivers set this value to <b>FALSE</b>. For more information about exclusive access, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563827">Specifying Exclusive Access to Device Objects</a>.


### -param DeviceObject [out]

Pointer to a variable that receives a pointer to the newly created <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. The <b>DEVICE_OBJECT</b> structure is allocated from nonpaged pool.


## -returns



<b>IoCreateDevice</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. A partial list of the failure codes returned by this function includes:




## -remarks



<b>IoCreateDevice</b> creates a device object and returns a pointer to the object. The caller is responsible for deleting the object when it is no longer needed by calling <a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>.

<b>IoCreateDevice</b> can only be used to create an unnamed device object, or a named device object for which a security descriptor is set by an INF file. Otherwise, drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a> to create named device objects. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542862">Creating a Device Object</a>. The caller is responsible for setting certain members of the returned device object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a> and the device-type-specific documentation for your device.

Be careful to specify the <i>DeviceType</i> and <i>DeviceCharacteristics</i> values in the correct parameters. Both parameters use system-defined FILE_<i>XXX</i> constants and some driver writers specify the values in the wrong parameters by mistake.

A remote file system that creates a named device object for a network redirector, and that registers using <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>, must specify FILE_REMOTE_DEVICE as one of the options in the <i>DeviceCharacteristics</i> parameter of <b>IoCreateDevice</b>.

Device objects for disks, tapes, CD-ROMs, and RAM disks are given a Volume Parameter Block (VPB) that is initialized to indicate that the volume has never been mounted on the device.

If a driver's call to <b>IoCreateDevice</b> returns an error, the driver should release any resources that it allocated for that device.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a>



<a href="..\wdm\ns-wdm-_device_object.md"> DEVICE_OBJECT</a>



<a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md">FsRtlRegisterUncProvider</a>



<a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>



<a href="..\wdm\nf-wdm-ioattachdevice.md">IoAttachDevice</a>



<a href="..\wdm\nf-wdm-iocreatesymboliclink.md">IoCreateSymbolicLink</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCreateDevice routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

