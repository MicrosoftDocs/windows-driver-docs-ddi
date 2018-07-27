---
UID: NF:spbcx.SpbDeviceInitConfig
title: SpbDeviceInitConfig function
author: windows-driver-content
description: The SpbDeviceInitConfig method attaches the SPB framework extension (SpbCx) to the I/O-request chain for a WDFDEVICE (FDO or PDO) object that is to be created.
old-location: spb\spbdeviceinitconfig.htm
tech.root: SPB
ms.assetid: 7B62C0B0-F90A-41B1-B903-5C9F905F4A08
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: SPB.spbdeviceinitconfig, SpbDeviceInitConfig, SpbDeviceInitConfig method [Buses], spbcx/SpbDeviceInitConfig
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	spbcxstubs.lib
-	spbcxstubs.dll
api_name:
-	SpbDeviceInitConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpbDeviceInitConfig function


## -description


The <b>SpbDeviceInitConfig</b> method attaches the SPB framework extension (SpbCx) to the I/O-request chain for a WDFDEVICE (FDO or PDO) object that is to be created.


## -parameters




### -param DeviceInit [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that is  to be configured.


## -returns



<b>SpbDeviceInitConfig</b> returns STATUS_SUCCESS if the call is successful.  Possible return values include the following error code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Cannot allocate the required system resources.

</td>
</tr>
</table>
 




## -remarks



This method associates the configuration information for SpbCx with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure for the device object (PDO or FDO) that is to be created. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback routine should call <b>SpbDeviceInitConfig</b> before it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> method to create the device object.


#### Examples

The following code example shows how to use the <b>SpbDeviceInitConfig</b> method to associate the SpbCx framework extension's configuration information with the <b>WDFDEVICE_INIT</b> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// FxDeviceInit is a pointer to a WDFDEVICE_INIT structure that comes as a
// parameter for an EvtDriverDeviceAdd handler, or from WdfPdoInitAllocate.
//

status = SpbDeviceInitConfig(FxDeviceInit);

if (!NT_SUCCESS(status))
{
    return status;
}

// 
// Set WDF and SpbCx device-level configuration options.
//

...

//
// Call WdfDeviceCreate
//

status = WdfDeviceCreate(&amp;FxDeviceInit,...);

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548786">WdfPdoInitAllocate</a>
 

 

