---
UID: NF:ndis.NdisTerminateWrapper
tech.root: 
title: NdisTerminateWrapper
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
 - NdisTerminateWrapper
f1_keywords:
 - NdisTerminateWrapper
 - ndis/NdisTerminateWrapper
dev_langs:
 - c++
helpviewer_keywords:
 - NdisTerminateWrapper
---

# NdisTerminateWrapper function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisTerminateWrapper** releases system resources allocated when the NIC driver called [**NdisMInitializeWrapper**](ff553547\(v=vs.85\).md).

## -parameters

### -param NdisWrapperHandle [in]

Specifies the handle returned by **NdisMInitializeWrapper**.

### -param SystemSpecific [in]

Pointer to an OS-specific type. For Windows 2000 and later drivers, this parameter should be **NULL**.

## -remarks

From its **DriverEntry** function, a miniport driver calls [**NdisMInitializeWrapper**](ff553547\(v=vs.85\).md) to notify NDIS that the driver is about to register itself as a miniport driver. After **NdisMInitializeWrapper** successfully returns, the miniport driver calls either [**NdisMRegisterMiniport**](ff553602\(v=vs.85\).md) or [**NdisIMRegisterLayeredMiniport**](ff552205\(v=vs.85\).md) to register its entry points with NDIS.

If a miniport driver's call to **NdisMRegisterMiniport** or **NdisIMRegisterLayeredMiniport** does not return NDIS\_STATUS\_SUCCESS, the miniport driver must call **NdisTerminateWrapper**. Calling **NdisTerminateWrapper** causesNDIS to clean up the resources that it allocated when the miniport driver called **NdisMInitializeWrapper**.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**DriverEntry of NDIS Miniport Drivers**](https://msdn.microsoft.com/library/Ff548818)
- [**MiniportHalt**](ff549451\(v=vs.85\).md)
- [**MiniportInitialize**](ff550472\(v=vs.85\).md)
- [**NdisMInitializeWrapper**](ff553547\(v=vs.85\).md)
 