---
UID: NF:ndis.NdisMRegisterDevice
tech.root: 
title: NdisMRegisterDevice
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisMRegisterDevice
f1_keywords:
 - NdisMRegisterDevice
 - ndis/NdisMRegisterDevice
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMRegisterDevice
---

# NdisMRegisterDevice function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

The **NdisMRegisterDevice** function creates a named device object and a symbolic link between the device object and a user-visible name for that device.

## -parameters

### -param NdisWrapperHandle [in]

Specifies the handle returned by [**NdisMInitializeWrapper**](https://msdn.microsoft.com/library/ff553547\(v=vs.85\)).

### -param DeviceName [in]

Pointer to an NDIS\_STRING type containing a null-terminated Unicode string that names the device object. The string must be a full-path name--for example, *\\Device\\DeviceName*. For Windows 2000 and later, NDIS defines the NDIS\_STRING type as a [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879) type.

### -param SymbolicName [in]

Pointer to an NDIS\_STRING type containing a Unicode string that is the Win32-visible name of the device being registered. Typically, the *SymbolicName* has the following format: *\\DosDevices\\SymbolicName*.

### -param MajorFunctions [in]

Pointer to an array of one or more entry points for the device driver's dispatch routines. A driver must set as many separate dispatch entry points as the IRP\_MJ\_*XXX* codes that the driver handles for the device object. Each dispatch routine is declared as follows:

```cpp
NTSTATUS
(*PDRIVER_DISPATCH) (
    IN PDEVICE_OBJECT Device Object,
    IN PIRP Irp
)   ;
```

A driver must not supply entry points for Plug and Play or Power Management handlers since the created device object is not for a physical device and therefore does not receive Plug and Play or Power Management IRPs.

### -param pDeviceObject [in]

Pointer to the newly created device object if the call succeeds.

### -param NdisDeviceHandle [out]

Pointer to a caller-supplied variable in which this function, if it succeeds, returns a handle to the device object. This handle is a required parameter to the [**NdisMDeregisterDevice**](nf-ndis-ndismderegisterdevice.md) function that the driver calls subsequently.

## -returns

**NdisMRegisterDevice** returns STATUS\_SUCCESS if it succeeds, NDIS\_STATUS\_NOT\_SUPPORTED if the caller is not an NDIS miniport driver, or a failure code if it fails.

## -remarks

An intermediate driver or miniport driver may require a separate, stand-alone device object. For example, an intermediate miniport driver might require a stand-alone device object to monitor the status of an underlying NIC when the NIC's miniport driver is not up and running. To obtain the NIC's status in such a case, a user-mode application or environmental subsystem sends an IRP to the device object. The IRP is processed by the intermediate driver. Without the stand-alone device object, the NIC's status is available only when the NIC's miniport driver is up and running.

An intermediate driver or miniport driver creates a device object by calling **NdisMRegisterDevice** from its **DriverEntry** function after **DriverEntry** has called [**NdisMInitializeWrapper**](https://msdn.microsoft.com/library/ff553547\(v=vs.85\)). **NdisMRegisterDevice** creates a named device object and also a symbolic link between the device object name and a user-visible name for that device. If the call to **NdisMRegisterDevice** succeeds, the I/O manager allocates storage in nonpaged pool for the device object itself and for all other data structures associated with the device object, including the driver's device extension. The device extension for an object created with **NdisMRegisterDevice** is reserved for use by NDIS and cannot be used by the driver.

A device object created with **NdisMRegisterDevice** functions in the same way as a device object and symbolic link that were created with [**IoCreateDevice**](https://msdn.microsoft.com/library/Ff548397) and [**IoCreateSymbolicLink**](https://msdn.microsoft.com/library/Ff549043), respectively. The miniport driver is responsible for processing all IRPs that it receives for the device object. (NDIS processes all Plug and Play and power management IRPs sent to the device object.) The driver processes IRPs sent to the device object using dispatch routines that it registered when it supplied the *MajorFunctions* pointer to **NdisMRegisterDevice**. For more information about device objects, IRPs, and dispatch routines, see [Device Objects and Device Stacks](https://msdn.microsoft.com/library/Ff543153), [Handling IRPs](https://msdn.microsoft.com/library/Ff546847), and [Writing Dispatch Routines](https://msdn.microsoft.com/library/Ff566407).

NDIS miniport and intermediate drivers should never call [**IoCreateDevice**](https://msdn.microsoft.com/library/Ff548397) or [**IoCreateSymbolicLink**](https://msdn.microsoft.com/library/Ff549043). Instead, if an NDIS driver must create a device object, it should call **NdisMRegisterDevice**. Miniport and intermediate drivers should never attempt to stack the device object over the physical device object by calling [**IoAttachDevice**](https://msdn.microsoft.com/library/Ff548294).

The device object that is created with **NdisMRegisterDevice** is not a physical device object and therefore does not receive Plug and Play or Power Management IRPs. Callers of **NdisMRegisterDevice** must therefore omit entry points for Plug and Play or Power Management handlers in the array that is pointed to by *MajorFunctions*.

Note that, if a handle to the device object that is created with **NdisMRegisterDevice** is open, the driver that created the device object cannot be unloaded. A user-mode application should therefore do either of the following:

1.  When the application registers for device event notification on the underlying device by calling the **RegisterDeviceNotification** function, specify a DBT\_DEVTYP\_HANDLE type notification filter. (For more information about the **RegisterDeviceNotification** function, see the Microsoft Windows SDK documentation.) If the application subsequently receives a DBT\_DEVICEQUERYREMOVE event for the device, the application should close the open handle.

2.  When the application registers for device event notification on the underlying device by calling the **RegisterDeviceNotification** function, specify a DBT\_DEVTYP\_DEVICEINTERFACE type notification filter and GUID\_NDIS\_LAN\_CLASS as the interface class GUID. If the application subsequently receives a DBT\_DEVICEREMOVECOMPLETE event for the device interface to which the handle corresponds, the application should close the open handle.

If a driver's call to **NdisMRegisterDevice** fails, the driver can continue to load or not, depending on how critical the stand-alone device object is for the driver's operation.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff564518"><strong>NdisRegisterDeviceEx</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**DriverEntry of NDIS Miniport Drivers**](https://msdn.microsoft.com/library/Ff548818)
- [**IoAttachDevice**](https://msdn.microsoft.com/library/Ff548294)
- [**IoCreateDevice**](https://msdn.microsoft.com/library/Ff548397)
- [**IoCreateSymbolicLink**](https://msdn.microsoft.com/library/Ff549043)
- [**NdisMDeregisterDevice**](nf-ndis-ndismderegisterdevice.md)
- [**NdisMInitializeWrapper**](https://msdn.microsoft.com/library/ff553547\(v=vs.85\))
- [**NdisRegisterDeviceEx**](https://msdn.microsoft.com/library/Ff564518)
- [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879)
