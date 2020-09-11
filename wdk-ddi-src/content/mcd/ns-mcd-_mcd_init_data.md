---
UID: NS:mcd._MCD_INIT_DATA
title: _MCD_INIT_DATA (mcd.h)
description: The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver.
old-location: storage\mcd_init_data.htm
tech.root: storage
ms.assetid: 4fc4c36f-a2ad-4b9f-a30b-e7ed600c38e9
ms.date: 03/29/2018
keywords: ["MCD_INIT_DATA structure"]
ms.keywords: "*PMCD_INIT_DATA, MCD_INIT_DATA, MCD_INIT_DATA structure [Storage Devices], PMCD_INIT_DATA, PMCD_INIT_DATA structure pointer [Storage Devices], _MCD_INIT_DATA, mcd/MCD_INIT_DATA, mcd/PMCD_INIT_DATA, storage.mcd_init_data, structs-changer_f8810f4b-8465-4751-a885-cc68a88e45fb.xml"
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
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
f1_keywords:
 - _MCD_INIT_DATA
 - mcd/_MCD_INIT_DATA
 - PMCD_INIT_DATA
 - mcd/PMCD_INIT_DATA
 - MCD_INIT_DATA
 - mcd/MCD_INIT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mcd.h
api_name:
 - MCD_INIT_DATA
---

# _MCD_INIT_DATA structure


## -description

The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver.

## -struct-fields

### -field InitDataSize

Size of this structure in bytes.

### -field ChangerAdditionalExtensionSize

Pointer to changer miniclass driver routine that returns the number of bytes the changer miniclass driver requires to store device-specific information in the device extension. This routine has the following prototype:


```
typedef
ULONG
(*CHANGER_EXTENSION_SIZE)(
  IN VOID
  );
```


### -field ChangerInitialize

Pointer to changer miniclass driver routine that does miniclass driver-specific initialization and readies the changer to receive other requests. This routine has the following prototype:


```
typedef 
NTSTATUS
(*CHANGER_INITIALIZE)(
  IN PDEVICE_OBJECT  DeviceObject
  );
```


### -field ChangerError

Pointer to changer miniclass driver routine that does device-specific error processing. This routine has the following prototype:


```
typedef
VOID
(*CHANGER_ERROR_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PSCSI_REQUEST_BLOCK  Srb,
  IN NTSTATUS  *Status,
  IN BOOLEAN  *Retry
  );
```


### -field ChangerPerformDiagnostics

Pointer to changer miniclass driver routine that performs diagnostic tests on the device. This routine has the following prototype:


```
typedef 
NTSTATUS
(*CHANGER_PERFORM_DIAGNOSTICS)(
  IN PDEVICE_OBJECT  DeviceObject,
  OUT PWMI_CHANGER_PROBLEM_DEVICE_ERROR  changerDeviceError
  );
```


### -field ChangerGetParameters

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_parameters">IOCTL_CHANGER_GET_PARAMETERS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerGetStatus

Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_status">IOCTL_CHANGER_GET_STATUS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerGetProductData

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_product_data">IOCTL_CHANGER_GET_PRODUCT_DATA</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerSetAccess

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_access">IOCTL_CHANGER_SET_ACCESS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerGetElementStatus

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerInitializeElementStatus

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_initialize_element_status">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerSetPosition

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_position">IOCTL_CHANGER_SET_POSITION</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerExchangeMedium

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_exchange_medium">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerMoveMedium

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_move_medium">IOCTL_CHANGER_MOVE_MEDIUM</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerReinitializeUnit

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_reinitialize_transport">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


### -field ChangerQueryVolumeTags

Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_query_volume_tags">IOCTL_CHANGER_QUERY_VOLUME_TAGS</a>. This routine has the following prototype:


```
typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );
```


## -remarks

This structure is used by the changer driver in Windows XP and later operating systems only.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changeradditionalextensionsize">ChangerAdditionalExtensionSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changererror">ChangerError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerexchangemedium">ChangerExchangeMedium</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetparameters">ChangerGetParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetproductdata">ChangerGetProductData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetstatus">ChangerGetStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitialize">ChangerInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitializeelementstatus">ChangerInitializeElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changermovemedium">ChangerMoveMedium</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerperformdiagnostics">ChangerPerformDiagnostics</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerreinitializeunit">ChangerReinitializeUnit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changersetaccess">ChangerSetAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changersetposition">ChangerSetPosition</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_exchange_medium">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_parameters">IOCTL_CHANGER_GET_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_product_data">IOCTL_CHANGER_GET_PRODUCT_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_status">IOCTL_CHANGER_GET_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_initialize_element_status">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_move_medium">IOCTL_CHANGER_MOVE_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_access">IOCTL_CHANGER_SET_ACCESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_position">IOCTL_CHANGER_SET_POSITION</a>

