---
UID: NA:mcd
ms.assetid: d0f47be9-5c97-3970-aeb3-d7c1f17ca997
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Mcd.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Mcd.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [ChangerAdditionalExtensionSize function](nf-mcd-changeradditionalextensionsize.md) | ChangerAdditionalExtensionSize indicates the number of bytes the changer miniclass driver requires to store device-specific information in the device extension. |
| [ChangerClassAllocatePool function](nf-mcd-changerclassallocatepool.md) | The ChangerClassAllocatePool function allocates pool memory. |
| [ChangerClassCreate function](nf-mcd-changerclasscreate.md) | The ChangerClassCreate routine is called by a changer minidriver to allow the class driver perform device-independent operations needed to create or close a device. |
| [ChangerClassDebugPrint function](nf-mcd-changerclassdebugprint.md) | The ChangerClassDebugPrint function prints debugging information. |
| [ChangerClassDeviceControl function](nf-mcd-changerclassdevicecontrol.md) | The ChangerClassDeviceControl routine is called by a changer minidriver to allow the class driver perform device-independent aspects of a device control operation. |
| [ChangerClassFreePool function](nf-mcd-changerclassfreepool.md) | The ChangerClassFreePool routine frees pool memory previously allocated using ChangerClassAllocatePool. |
| [ChangerClassInitialize function](nf-mcd-changerclassinitialize.md) | The ChangerClassInitialize routine initializes the driver. |
| [ChangerClassSendSrbSynchronous function](nf-mcd-changerclasssendsrbsynchronous.md) | The ChangerClassSendSrbSynchronous routine synchronously sends an SRB to a specified device. |
| [ChangerError function](nf-mcd-changererror.md) | ChangerError performs device-specific error handling. |
| [ChangerExchangeMedium function](nf-mcd-changerexchangemedium.md) | ChangerExchangeMedium handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_EXCHANGE_MEDIUM. |
| [ChangerGetElementStatus function](nf-mcd-changergetelementstatus.md) | ChangerGetElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_ELEMENT_STATUS. |
| [ChangerGetParameters function](nf-mcd-changergetparameters.md) | ChangerGetParameters handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PARAMETERS. |
| [ChangerGetProductData function](nf-mcd-changergetproductdata.md) | ChangerGetProductData handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PRODUCT_DATA. |
| [ChangerGetStatus function](nf-mcd-changergetstatus.md) | ChangerGetStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_STATUS. |
| [ChangerInitialize function](nf-mcd-changerinitialize.md) | ChangerInitialize readies the changer to receive other requests. |
| [ChangerInitializeElementStatus function](nf-mcd-changerinitializeelementstatus.md) | ChangerInitializeElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS. |
| [ChangerMoveMedium function](nf-mcd-changermovemedium.md) | ChangerMoveMedium handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_MOVE_MEDIUM. |
| [ChangerPerformDiagnostics function](nf-mcd-changerperformdiagnostics.md) | ChangerPerformDiagnostics performs diagnostic tests on the changer device. |
| [ChangerQueryVolumeTags function](nf-mcd-changerqueryvolumetags.md) | ChangerQueryVolumeTags handles the device-specific aspects of a device-control IRP with the IOCTL code of IOCTL_CHANGER_QUERY_VOLUME_TAGS. |
| [ChangerReinitializeUnit function](nf-mcd-changerreinitializeunit.md) | ChangerReinitializeUnit handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_REINITIALIZE_TRANSPORT. |
| [ChangerSetAccess function](nf-mcd-changersetaccess.md) | ChangerSetAccess handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_ACCESS. |
| [ChangerSetPosition function](nf-mcd-changersetposition.md) | ChangerSetPosition handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_POSITION. |
| [DriverEntry function](nf-mcd-driverentry.md) | The DriverEntry miniport driver routine is called when the miniport driver is loaded.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_MCD_INIT_DATA structure](ns-mcd-_mcd_init_data.md) | The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver. |
