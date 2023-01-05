---
UID: NF:ndis.NdisMInitializeWrapper
tech.root: netvista
title: NdisMInitializeWrapper
ms.date: 01/04/2023
targetos: Windows
description: NdisMInitializeWrapper notifies NDIS that a new miniport driver is initializing.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
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
 - NdisMInitializeWrapper
f1_keywords:
 - NdisMInitializeWrapper
 - ndis/NdisMInitializeWrapper
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMInitializeWrapper
---

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

NdisMInitializeWrapper notifies NDIS that a new miniport driver is initializing.

## -parameters

### -param _a [out]

Pointer to a caller-supplied variable in which NDIS returns a handle that represents itself. If the call to **NdisMInitializeWrapper** fails, NDIS sets the variable at NdisWrapperHandle to **NULL**.

### -param _b [in]

Specifies a pointer of a system-specific type.

For Windows 2000 and later drivers, this is a pointer to an opaque driver object input to the miniport driver's **DriverEntry** function.

### -param _c [in]

Specifies a pointer of a system-specific type.

For Windows 2000 and later drivers, this is a pointer to an opaque registry path input to the miniport driver's **DriverEntry** function.

### -param _d [in]

Specifies a pointer of a system-specific type.

For Windows 2000 and later drivers, this pointer should be set to **NULL** when the miniport driver calls **NdisMInitializeWrapper**.

## -syntax

```cpp
VOID NdisInitializeWrapper(
  _Out_ PNDIS_HANDLE  NdisWrapperHandle,
  _In_ PVOID SystemSpecific1,
  _In_ PVOID SystemSpecific2,
  _In_ PVOID SystemSpecific3
);
```

## -remarks

A NIC driver or intermediate driver must call **NdisMInitializeWrapper** before it calls any other NdisXxx function. Usually, this call is the initial action of any NIC driver's **DriverEntry** function, which calls [**NdisMRegisterMiniport**](/previous-versions/windows/hardware/network/ff553602(v=vs.85)) or [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md) with the returned *NdisWrapperHandle* next. NDIS intermediate drivers also must call **NdisMInitializeWrapper** from the **DriverEntry** function and, then, call **NdisMRegisterMiniport** or **NdisIMRegisterLayeredMiniport** with the returned *NdisWrapperHandle*.

Such a driver's subsequent calls to *NdisXxx* initialization and configuration functions must pass the *NdisWrapperHandle* as a parameter. Consequently, it is an input parameter to the [**MiniportInitialize**](/previous-versions/windows/hardware/network/ff550472(v=vs.85)) function.

If the call to **NdisMInitializeWrapper** fails, NDIS sets the variable at *NdisWrapperHandle* to **NULL**. The driver should always check the value of this variable after **NdisMInitializeWrapper** returns. If the value is **NULL**, the driver should fail the call to the **DriverEntry** function.

## -see-also

[**Initializing a Miniport Driver**](/windows-hardware/drivers/network/initializing-a-miniport-driver)

[**NdisMRegisterMiniport**](/previous-versions/windows/hardware/network/ff553602(v=vs.85))

[**MiniportInitialize**](/previous-versions/windows/hardware/network/ff550472(v=vs.85))

[**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md)

[**NdisTerminateWrapper**](nf-ndis-ndisterminatewrapper.md)