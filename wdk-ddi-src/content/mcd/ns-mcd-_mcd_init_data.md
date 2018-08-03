---
UID: NS:mcd._MCD_INIT_DATA
title: "_MCD_INIT_DATA"
author: windows-driver-content
description: The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver.
old-location: storage\mcd_init_data.htm
tech.root: storage
ms.assetid: 4fc4c36f-a2ad-4b9f-a30b-e7ed600c38e9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMCD_INIT_DATA, MCD_INIT_DATA, MCD_INIT_DATA structure [Storage Devices], PMCD_INIT_DATA, PMCD_INIT_DATA structure pointer [Storage Devices], _MCD_INIT_DATA, mcd/MCD_INIT_DATA, mcd/PMCD_INIT_DATA, storage.mcd_init_data, structs-changer_f8810f4b-8465-4751-a885-cc68a88e45fb.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mcd.h
req.include-header: Mcd.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	MCD_INIT_DATA
product:
- Windows
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# _MCD_INIT_DATA structure


## -description


The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver. 


## -struct-fields




### -field InitDataSize

Size of this structure in bytes. 


### -field ChangerAdditionalExtensionSize

Pointer to changer miniclass driver routine that returns the number of bytes the changer miniclass driver requires to store device-specific information in the device extension. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
ULONG
(*CHANGER_EXTENSION_SIZE)(
  IN VOID
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerInitialize

Pointer to changer miniclass driver routine that does miniclass driver-specific initialization and readies the changer to receive other requests. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef 
NTSTATUS
(*CHANGER_INITIALIZE)(
  IN PDEVICE_OBJECT  DeviceObject
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerError

Pointer to changer miniclass driver routine that does device-specific error processing. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*CHANGER_ERROR_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PSCSI_REQUEST_BLOCK  Srb,
  IN NTSTATUS  *Status,
  IN BOOLEAN  *Retry
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerPerformDiagnostics

Pointer to changer miniclass driver routine that performs diagnostic tests on the device. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef 
NTSTATUS
(*CHANGER_PERFORM_DIAGNOSTICS)(
  IN PDEVICE_OBJECT  DeviceObject,
  OUT PWMI_CHANGER_PROBLEM_DEVICE_ERROR  changerDeviceError
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerGetParameters

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerGetStatus

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559405">IOCTL_CHANGER_GET_STATUS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerGetProductData

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559402">IOCTL_CHANGER_GET_PRODUCT_DATA</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerSetAccess

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559422">IOCTL_CHANGER_SET_ACCESS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerGetElementStatus

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559396">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerInitializeElementStatus

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559409">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerSetPosition

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559425">IOCTL_CHANGER_SET_POSITION</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerExchangeMedium

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559391">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerMoveMedium

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559410">IOCTL_CHANGER_MOVE_MEDIUM</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerReinitializeUnit

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559419">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

### -field ChangerQueryVolumeTags

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559417">IOCTL_CHANGER_QUERY_VOLUME_TAGS</a>. This routine has the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>

## -remarks



This structure is used by the changer driver in Windows XP and later operating systems only. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551400">ChangerAdditionalExtensionSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551418">ChangerError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551421">ChangerExchangeMedium</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551424">ChangerGetElementStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551425">ChangerGetParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551427">ChangerGetProductData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551429">ChangerGetStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551431">ChangerInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551433">ChangerInitializeElementStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551436">ChangerMoveMedium</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551438">ChangerPerformDiagnostics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551440">ChangerQueryVolumeTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551443">ChangerReinitializeUnit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551447">ChangerSetAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551449">ChangerSetPosition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559391">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559396">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559402">IOCTL_CHANGER_GET_PRODUCT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559405">IOCTL_CHANGER_GET_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559409">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559410">IOCTL_CHANGER_MOVE_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559422">IOCTL_CHANGER_SET_ACCESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559425">IOCTL_CHANGER_SET_POSITION</a>
 

 

