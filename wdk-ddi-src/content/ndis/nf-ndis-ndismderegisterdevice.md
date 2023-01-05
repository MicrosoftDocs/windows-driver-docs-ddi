---
UID: NF:ndis.NdisMDeregisterDevice
tech.root: netvista
title: NdisMDeregisterDevice
ms.date: 01/04/2023
targetos: Windows
description: The NdisMDeregisterDevice function removes from the system a device object that was created with NdisMRegisterDevice.
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
 - NdisMDeregisterDevice
f1_keywords:
 - NdisMDeregisterDevice
 - ndis/NdisMDeregisterDevice
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMDeregisterDevice
---
# NdisMDeregisterDevice function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

The **NdisMDeregisterDevice** function removes from the system a device object that was created with [**NdisMRegisterDevice**](nf-ndis-ndismregisterdevice.md). **NdisMDeregisterDevice** also removes the symbolic link that is associated with this device object.

## -parameters

### -param NdisDeviceHandle [in]

Specifies the handle returned by **NdisMRegisterDevice** that identifies the device object to be deregistered.

## -returns

**NdisMDeregisterDevice** returns NDIS\_STATUS\_SUCCESS if the device object and its associated symbolic link object are deleted.

## -remarks

A driver calls **NdisMDeregisterDevice** from its **Halt** or **Unload** function to deregister a stand-alone device object that it previously created with [**NdisMRegisterDevice**](nf-ndis-ndismregisterdevice.md). The driver must call **NdisMDeregisterDevice** when it is being unloaded or when its **DriverEntry** routine encounters a fatal initialization error, such as an inability to obtain system resources.

When **NdisMRegisterDevice** is called, there cannot be any outstanding user-mode open operations on the device object being deleted. If there are, a system error occurs.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**MiniportHalt**](previous-versions/windows/embedded/aa447845(v=msdn.10))
- [**NdisMRegisterDevice**](nf-ndis-ndismregisterdevice.md)
- [**NdisMRegisterUnloadHandler**](nf-ndis-ndismregisterunloadhandler.md)
