---
UID: NS:mcd._MCD_INIT_DATA
title: "_MCD_INIT_DATA"
author: windows-driver-content
description: The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver.
old-location: storage\mcd_init_data.htm
old-project: storage
ms.assetid: 4fc4c36f-a2ad-4b9f-a30b-e7ed600c38e9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PMCD_INIT_DATA, ,, A, C, D, I, M, MCD_INIT_DATA, MCD_INIT_DATA structure [Storage Devices], N, P, PMCD_INIT_DATA, PMCD_INIT_DATA structure pointer [Storage Devices], T, _, _MCD_INIT_DATA, mcd/MCD_INIT_DATA, mcd/PMCD_INIT_DATA, storage.mcd_init_data, structs-changer_f8810f4b-8465-4751-a885-cc68a88e45fb.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mcd.h
apiname:
-	MCD_INIT_DATA
product: Windows
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# _MCD_INIT_DATA structure


## -description


The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver. 


## -syntax


````
typedef struct _MCD_INIT_DATA {
  ULONG                       InitDataSize;
  CHANGER_EXTENSION_SIZE      ChangerAdditionalExtensionSize;
  CHANGER_INITIALIZE          ChangerInitialize;
  CHANGER_ERROR_ROUTINE       ChangerError;
  CHANGER_PERFORM_DIAGNOSTICS ChangerPerformDiagnostics;
  CHANGER_COMMAND_ROUTINE     ChangerGetParameters;
  CHANGER_COMMAND_ROUTINE     ChangerGetStatus;
  CHANGER_COMMAND_ROUTINE     ChangerGetProductData;
  CHANGER_COMMAND_ROUTINE     ChangerSetAccess;
  CHANGER_COMMAND_ROUTINE     ChangerGetElementStatus;
  CHANGER_COMMAND_ROUTINE     ChangerInitializeElementStatus;
  CHANGER_COMMAND_ROUTINE     ChangerSetPosition;
  CHANGER_COMMAND_ROUTINE     ChangerExchangeMedium;
  CHANGER_COMMAND_ROUTINE     ChangerMoveMedium;
  CHANGER_COMMAND_ROUTINE     ChangerReinitializeUnit;
  CHANGER_COMMAND_ROUTINE     ChangerQueryVolumeTags;
} MCD_INIT_DATA, *PMCD_INIT_DATA;
````


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

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_parameters.md">IOCTL_CHANGER_GET_PARAMETERS</a>. This routine has the following prototype:

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

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_status.md">IOCTL_CHANGER_GET_STATUS</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md">IOCTL_CHANGER_SET_ACCESS</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_initialize_element_status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_position.md">IOCTL_CHANGER_SET_POSITION</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_exchange_medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_reinitialize_transport.md">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. This routine has the following prototype:

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

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code of <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_query_volume_tags.md">IOCTL_CHANGER_QUERY_VOLUME_TAGS</a>. This routine has the following prototype:

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

<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_parameters.md">IOCTL_CHANGER_GET_PARAMETERS</a>



<a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a>



<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>



<a href="..\mcd\nf-mcd-changergetparameters.md">ChangerGetParameters</a>



<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>



<a href="..\mcd\nf-mcd-changerinitialize.md">ChangerInitialize</a>



<a href="..\mcd\nf-mcd-changererror.md">ChangerError</a>



<a href="..\mcd\nf-mcd-changersetaccess.md">ChangerSetAccess</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_exchange_medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>



<a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_status.md">IOCTL_CHANGER_GET_STATUS</a>



<a href="..\mcd\nf-mcd-changergetstatus.md">ChangerGetStatus</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_initialize_element_status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>



<a href="..\mcd\nf-mcd-changerreinitializeunit.md">ChangerReinitializeUnit</a>



<a href="..\mcd\nf-mcd-changermovemedium.md">ChangerMoveMedium</a>



<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>



<a href="..\mcd\nf-mcd-changeradditionalextensionsize.md">ChangerAdditionalExtensionSize</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_position.md">IOCTL_CHANGER_SET_POSITION</a>



<a href="..\mcd\nf-mcd-changersetposition.md">ChangerSetPosition</a>



<a href="..\mcd\nf-mcd-changergetproductdata.md">ChangerGetProductData</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md">IOCTL_CHANGER_SET_ACCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MCD_INIT_DATA structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

