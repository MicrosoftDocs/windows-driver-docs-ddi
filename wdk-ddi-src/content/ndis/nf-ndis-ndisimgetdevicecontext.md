---
UID: NF:ndis.NdisIMGetDeviceContext
tech.root: 
title: NdisIMGetDeviceContext
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
req.include-header: 
req.irql: 
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
 - NdisIMGetDeviceContext
f1_keywords:
 - NdisIMGetDeviceContext
 - ndis/NdisIMGetDeviceContext
dev_langs:
 - c++
helpviewer_keywords:
 - NdisIMGetDeviceContext
---

# NdisIMGetDeviceContext (Windows CE 5.0)

## -description

This function allows an NDIS intermediate driver's [MiniportInitialize](aa447847\(v=msdn.10\).md) function to access the device context area allocated by its [ProtocolBindAdapter](ms919689\(v=msdn.10\).md) function.

## -parameters

### -param MiniportAdapterHandle [in]

Specifies the handle input to **MiniportInitialize**.

## -returns

The following table shows the return values for this function.

<table>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>NDISIMGETDEVICECONTEXT</td>
<td>Returns access to the device context area for the virtual NIC identified by <em>MiniportAdapterHandle</em>.</td>
</tr>
<tr class="even">
<td>NULL</td>
<td>If the driver's ProtocolBindAdapter function did not allocate such a device context area.</td>
</tr>
</tbody>
</table>

## -remarks

An NDIS intermediate driver's **MiniportInitialize** function calls **NdisIMGetDeviceContext** to access the device context area for the virtual NIC it is initializing. Usually, the memory for such an area is provided by the intermediate driver's **ProtocolBindAdapter** function, which calls [NdisIMInitializeDeviceInstanceEx](aa447997\(v=msdn.10\).md) with a pointer to this area, thereby causing the driver's **MiniportInitialize** function to be called. However, an intermediate driver is not required to have such a context area.

On return from **NdisIMGetDeviceContext**, **MiniportInitialize** sets up the driver-defined state for the virtual NIC with whatever information the intermediate driver writer intends to be useful to still higher-level protocols that bind themselves subsequently to its virtual NIC.

Still higher level NDIS protocols bound to the same virtual NIC subsequently can access this device context area by calling [NdisIMGetBindingContext](aa447993\(v=msdn.10\).md) from their **ProtocolBindAdapter** functions.

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [MiniportInitialize](aa447847\(v=msdn.10\).md)
- [NdisIMGetBindingContext](aa447993\(v=msdn.10\).md)
- [NdisIMInitializeDeviceInstanceEx](aa447997\(v=msdn.10\).md)
- [ProtocolBindAdapter](ms919689\(v=msdn.10\).md)
