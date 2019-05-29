---
UID: NF:wdfpdo.WdfPdoInitAssignContainerID
title: WdfPdoInitAssignContainerID function (wdfpdo.h)
description: The WdfPdoInitAssignContainerID method updates the container ID for a child device.
old-location: wdf\wdfpdoinitassigncontainerid.htm
tech.root: wdf
ms.assetid: 603bff9f-fd18-40bd-9b2b-8f013f99ec61
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_b744c1d7-e24f-4936-8921-cf5b7dd4ad68.xml, WdfPdoInitAssignContainerID, WdfPdoInitAssignContainerID method, kmdf.wdfpdoinitassigncontainerid, wdf.wdfpdoinitassigncontainerid, wdfpdo/WdfPdoInitAssignContainerID
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoInitAssignContainerID
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitAssignContainerID function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitAssignContainerID</b> method updates the container ID for a child device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param ContainerID [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a container ID string. The driver can allocate the string's buffer from paged pool.


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
The driver could not allocate space to store the container ID string.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



For more information about container IDs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a>.

The driver must call <b>WdfPdoInitAssignContainerID</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure, stores a Unicode string in the structure, and then registers the Unicode string as the device's container ID.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING containerId = {0}; 

RtlInitUnicodeString(
                     &amp;containerId,
                     strContainerId //Unicode string for container ID
                     );
status = WdfPdoInitAssignContainerID(
                                     pDeviceInit,
                                     &amp;containerId
                                     );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548776">WdfPdoInitAddCompatibleID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548784">WdfPdoInitAddHardwareID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548797">WdfPdoInitAssignDeviceID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548799">WdfPdoInitAssignInstanceID</a>
 

 

