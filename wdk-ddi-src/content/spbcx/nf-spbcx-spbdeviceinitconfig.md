---
UID: NF:spbcx.SpbDeviceInitConfig
title: SpbDeviceInitConfig function
author: windows-driver-content
description: The SpbDeviceInitConfig method attaches the SPB framework extension (SpbCx) to the I/O-request chain for a WDFDEVICE (FDO or PDO) object that is to be created.
old-location: spb\spbdeviceinitconfig.htm
old-project: SPB
ms.assetid: 7B62C0B0-F90A-41B1-B903-5C9F905F4A08
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SpbDeviceInitConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SpbDeviceInitConfig
req.alt-loc: spbcxstubs.lib,spbcxstubs.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbDeviceInitConfig function



## -description
The <b>SpbDeviceInitConfig</b> method attaches the SPB framework extension (SpbCx) to the I/O-request chain for a WDFDEVICE (FDO or PDO) object that is to be created.



## -syntax

````
NTSTATUS SpbDeviceInitConfig(
  _Inout_ WDFDEVICE_INIT *DeviceInit
);
````


## -parameters

### -param DeviceInit [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that is  to be configured.


## -returns
<b>SpbDeviceInitConfig</b> returns STATUS_SUCCESS if the call is successful.  Possible return values include the following error code.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Cannot allocate the required system resources.

 


## -remarks
This method associates the configuration information for SpbCx with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure for the device object (PDO or FDO) that is to be created. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback routine should call <b>SpbDeviceInitConfig</b> before it calls the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method to create the device object.

The following code example shows how to use the <b>SpbDeviceInitConfig</b> method to associate the SpbCx framework extension's configuration information with the <b>WDFDEVICE_INIT</b> structure.


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>
</dt>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallocate.md">WdfPdoInitAllocate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbDeviceInitConfig method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

