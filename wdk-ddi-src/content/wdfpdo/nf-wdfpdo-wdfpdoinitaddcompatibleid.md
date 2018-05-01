---
UID: NF:wdfpdo.WdfPdoInitAddCompatibleID
title: WdfPdoInitAddCompatibleID function
author: windows-driver-content
description: The WdfPdoInitAddCompatibleID method adds a compatible ID to the list of compatible IDs for a child device.
old-location: wdf\wdfpdoinitaddcompatibleid.htm
old-project: wdf
ms.assetid: cf79661f-afe8-4154-8302-e5018172c6ec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_2578889b-85d3-4706-8907-817328ce8ad5.xml, WdfPdoInitAddCompatibleID, WdfPdoInitAddCompatibleID method, kmdf.wdfpdoinitaddcompatibleid, wdf.wdfpdoinitaddcompatibleid, wdfpdo/WdfPdoInitAddCompatibleID
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
-	WdfPdoInitAddCompatibleID
product: Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitAddCompatibleID function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAddCompatibleID</b> method adds a compatible ID to the list of compatible IDs for a child device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param CompatibleID [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a compatible ID string. The driver can allocate the string's buffer from paged pool.


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
The driver could not allocate space to store the compatible ID string.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The driver can add one or more compatible IDs for a device. They should be added in order, from best match to worst match. The framework will deliver the IDs to the PnP manager in the order that they were added. For more information about compatible IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

The driver must call <b>WdfPdoInitAddCompatibleID</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example reports a compatible ID value that the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample driver uses.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DECLARE_CONST_UNICODE_STRING(compatId, L"{B85B7C50-6A01-11d2-B841-00C04FAD5171}\\MsCompatibleToaster\0");

status = WdfPdoInitAddCompatibleID(
                                   DeviceInit,
                                   &amp;compatId
                                   );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548784">WdfPdoInitAddHardwareID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548797">WdfPdoInitAssignDeviceID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548799">WdfPdoInitAssignInstanceID</a>
 

 

