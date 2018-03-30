---
UID: NF:wdfpdo.WdfPdoInitAddHardwareID
title: WdfPdoInitAddHardwareID function
author: windows-driver-content
description: The WdfPdoInitAddHardwareID method adds a hardware ID to the list of hardware IDs for a child device.
old-location: wdf\wdfpdoinitaddhardwareid.htm
old-project: wdf
ms.assetid: 2b5c853d-8548-419e-bd41-be9e8364fb57
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_f06f24ea-f0f8-4ce7-8b70-725de7b5c970.xml, WdfPdoInitAddHardwareID, WdfPdoInitAddHardwareID method, kmdf.wdfpdoinitaddhardwareid, wdf.wdfpdoinitaddhardwareid, wdfpdo/WdfPdoInitAddHardwareID
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfPdoInitAddHardwareID
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoInitAddHardwareID function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAddHardwareID</b> method adds a hardware ID to the list of hardware IDs for a child device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param HardwareID [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a hardware ID string. The driver can allocate the string's buffer from paged pool.


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
The driver could not allocate space to store the hardware ID string.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The driver can add one or more hardware IDs for a device. They should be added in order from best match to worst match. The framework will deliver the IDs to the PnP manager in the order that they were added. For more information about hardware IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

The driver must call <b>WdfPdoInitAddHardwareID</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example reports a hardware ID that the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver uses.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define  KBFILTR_DEVICE_ID L"{A65C87F9-BE02-4ed9-92EC-012D416169FA}\\KeyboardFilter\0"
DECLARE_CONST_UNICODE_STRING(hardwareId, KBFILTR_DEVICE_ID);

status = WdfPdoInitAddHardwareID(
                                 pDeviceInit,
                                 &amp;hardwareId
                                 );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548776">WdfPdoInitAddCompatibleID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548797">WdfPdoInitAssignDeviceID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548799">WdfPdoInitAssignInstanceID</a>
 

 

