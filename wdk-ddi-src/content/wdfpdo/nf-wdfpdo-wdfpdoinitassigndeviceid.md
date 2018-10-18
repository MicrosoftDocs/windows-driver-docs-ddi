---
UID: NF:wdfpdo.WdfPdoInitAssignDeviceID
title: WdfPdoInitAssignDeviceID function
author: windows-driver-content
description: The WdfPdoInitAssignDeviceID method updates the device ID for a child device.
old-location: wdf\wdfpdoinitassigndeviceid.htm
tech.root: wdf
ms.assetid: f8992245-42db-4ca8-afdc-e123adc0a40d
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_c0885107-9e40-4c57-ab50-c757ea58b2f9.xml, WdfPdoInitAssignDeviceID, WdfPdoInitAssignDeviceID method, kmdf.wdfpdoinitassigndeviceid, wdf.wdfpdoinitassigndeviceid, wdfpdo/WdfPdoInitAssignDeviceID
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
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
-	WdfPdoInitAssignDeviceID
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitAssignDeviceID function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitAssignDeviceID</b> method updates the <a href="https://msdn.microsoft.com/a71b64bc-319e-4133-810b-7fd417cf0af8">device ID</a> for a child device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceID [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a device ID string. The driver can allocate the string's buffer from paged pool.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The driver is initializing an FDO instead of a PDO.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The driver could not allocate space to store the device ID string.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A device ID is typically the first item in the list of hardware IDs that a device reports. For more information about device IDs and hardware IDs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

The driver must call <b>WdfPdoInitAssignDeviceID</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example reports a device ID that the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver uses.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define  KBFILTR_DEVICE_ID L"{A65C87F9-BE02-4ed9-92EC-012D416169FA}\\KeyboardFilter\0"
DECLARE_CONST_UNICODE_STRING(deviceId,KBFILTR_DEVICE_ID);

status = WdfPdoInitAssignDeviceID(
                                  pDeviceInit,
                                  &amp;deviceId
                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548776">WdfPdoInitAddCompatibleID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548784">WdfPdoInitAddHardwareID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548799">WdfPdoInitAssignInstanceID</a>
 

 

