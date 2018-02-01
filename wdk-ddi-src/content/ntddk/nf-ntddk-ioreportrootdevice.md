---
UID: NF:ntddk.IoReportRootDevice
title: IoReportRootDevice function
author: windows-driver-content
description: The IoReportRootDevice routine reports a device that cannot be detected by a PnP bus driver to the PnP Manager. IoReportRootDevice allows only one device per driver to be created.
old-location: kernel\ioreportrootdevice.htm
old-project: kernel
ms.assetid: 43063BD3-8F2C-4F27-A304-75FBD5C87674
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoReportRootDevice routine [Kernel-Mode Driver Architecture], IoReportRootDevice, kernel.ioreportrootdevice, ntddk/IoReportRootDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoReportRootDevice
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoReportRootDevice function


## -description


The <b>IoReportRootDevice</b> routine reports a device that cannot be detected by a PnP bus driver to the PnP Manager.  <b>IoReportRootDevice</b> allows only one device per driver to be created.


## -syntax


````
NTSTATUS IoReportRootDevice(
  _In_ PDRIVER_OBJECT DriverObject
);
````


## -parameters




### -param DriverObject [in]

Pointer to the driver object of the driver that detected the device.


## -returns


<b>IoReportRootDevice</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.



## -remarks


Drivers for devices that cannot be detected by a PnP bus driver use <b>IoReportRootDevice</b> to report their device to the system. Devices that can be detected by a PnP bus driver should be reported in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request.

A driver typically calls this routine from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine.

<b>IoReportRootDevice</b> marks the device as a root-enumerated device and this identification is persistent across system boots. The PnP manager "detects" the device on the root-enumerated list and configures it like a PnP device: the PnP manager queries for device information, identifies the appropriate drivers and calls their <i>AddDevice</i> routines, and sends all the appropriate PnP IRPs.

The system generates a single Hardware ID string for the device, of the form ROOT\<i>Driver</i> where <i>Driver</i>  is the driver's service name. A driver can provide additional hardware IDs or compatible IDs by handling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551679">IRP_MN_QUERY_ID</a> request.

A driver writer must provide an INF file that matches any of the specified hardware IDs or compatible IDs. The INF file should specify the original driver that called <b>IoReportRootDevice</b> as the driver to load for those IDs. The system uses this information to rebuild the driver stack for the device, for example on restart. Callers of <b>IoReportRootDevice</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.


<div class="alert"><b>Note</b>  Drivers should use <a href="..\ntddk\nf-ntddk-ioreportdetecteddevice.md">IoReportDetectedDevice</a> to report hardware devices that use resources but cannot be detected by a PnP bus driver instead of <b>IoReportRootDevice</b>.</div>
<div> </div>




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551679">IRP_MN_QUERY_ID</a>

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>

<a href="..\ntddk\nf-ntddk-ioreportresourcefordetection.md">IoReportResourceForDetection</a>

<a href="..\ntddk\nf-ntddk-ioreportdetecteddevice.md">IoReportDetectedDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReportRootDevice routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

