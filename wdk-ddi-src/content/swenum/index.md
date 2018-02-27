---
UID: NA:swenum
ms.assetid: 631903f3-c726-3652-b341-ccbe7cdd2a44
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Swenum.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Swenum.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [KsCreateBusEnumObject function](nf-swenum-kscreatebusenumobject.md) | The KsCreateBusEnumObject function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services. |
| [KsDereferenceSoftwareBusObject function](nf-swenum-ksdereferencesoftwarebusobject.md) | The KsDereferenceSoftwareBusObject function decrements the reference count of the demand-load bus enumerator object's PDO. |
| [KsGetBusEnumIdentifier function](nf-swenum-ksgetbusenumidentifier.md) | The KsGetBusEnumIdentifier function retrieves the software bus enumerator identifier for the bus device associated with the given IRP. |
| [KsGetBusEnumParentFDOFromChildPDO function](nf-swenum-ksgetbusenumparentfdofromchildpdo.md) | The KsGetBusEnumParentFDOFromChildPDO function retrieves the FDO of the parent of the given child PDO. |
| [KsGetBusEnumPnpDeviceObject function](nf-swenum-ksgetbusenumpnpdeviceobject.md) | The KsGetBusEnumPnpDeviceObject function retrieves the Plug and Play device object attached to the given device object. |
| [KsInstallBusEnumInterface function](nf-swenum-ksinstallbusenuminterface.md) | The KsInstallBusEnumInterface function installs an interface to the demand-load bus enumerator object. |
| [KsIsBusEnumChildDevice function](nf-swenum-ksisbusenumchilddevice.md) | The KsIsBusEnumChildDevice function determines if the given device object is a child device of the demand-load bus enumerator object. |
| [KsQuerySoftwareBusInterface function](nf-swenum-ksquerysoftwarebusinterface.md) | The KsQuerySoftwareBusInterface function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer. |
| [KsReferenceSoftwareBusObject function](nf-swenum-ksreferencesoftwarebusobject.md) | The KsReferenceSoftwareBusObject function increments the reference count of the demand-load bus enumerator object's PDO. |
| [KsRemoveBusEnumInterface function](nf-swenum-ksremovebusenuminterface.md) | The KsRemoveBusEnumInterface function removes an interface to the demand-load bus enumerator object. |
| [KsServiceBusEnumCreateRequest function](nf-swenum-ksservicebusenumcreaterequest.md) | The KsServiceBusEnumCreateRequest function services IRP_MJ_CREATE requests for the software bus device interface. |
| [KsServiceBusEnumPnpRequest function](nf-swenum-ksservicebusenumpnprequest.md) | The KsServiceBusEnumPnpRequest function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with KsCreateBusEnumObject. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFNDEREFERENCEDEVICEOBJECT callback](nc-swenum-pfndereferencedeviceobject.md) | The driver can use this routine to decrement the reference count of the PDO. |
| [PFNQUERYREFERENCESTRING callback](nc-swenum-pfnqueryreferencestring.md) | This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool. |
| [PFNREFERENCEDEVICEOBJECT callback](nc-swenum-pfnreferencedeviceobject.md) | The driver can use this routine to increment the reference count of the PDO. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_BUS_INTERFACE_SWENUM structure](ns-swenum-_bus_interface_swenum.md) | The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface. |
| [_SWENUM_INSTALL_INTERFACE structure](ns-swenum-_swenum_install_interface.md) | The SWENUM_INSTALL_INTERFACE structure describes a specific demand-load bus enumerator object interface to install. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SWENUM_GET_BUS_ID IOCTL](ni-swenum-ioctl_swenum_get_bus_id.md) | TBD |
| [IOCTL_SWENUM_INSTALL_INTERFACE IOCTL](ni-swenum-ioctl_swenum_install_interface.md) | TBD |
| [IOCTL_SWENUM_REMOVE_INTERFACE IOCTL](ni-swenum-ioctl_swenum_remove_interface.md) | TBD |
