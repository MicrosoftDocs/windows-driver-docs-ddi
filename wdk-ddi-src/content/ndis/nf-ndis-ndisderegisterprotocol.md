---
UID: NF:ndis.NdisDeregisterProtocol
tech.root: 
title: NdisDeregisterProtocol
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
 - NdisDeregisterProtocol
f1_keywords:
 - NdisDeregisterProtocol
 - ndis/NdisDeregisterProtocol
dev_langs:
 - c++
helpviewer_keywords:
 - NdisDeregisterProtocol
---

# NdisDeregisterProtocol function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisDeregisterProtocol** releases the resources allocated when the driver called **NdisRegisterProtocol**.

## -parameters

### -param Status

Pointer to a caller-supplied variable that is set to NDIS\_STATUS\_SUCCESS on return from this function.

### -param NdisProtocolHandle

Specifies the handle returned by [**NdisRegisterProtocol**](nf-ndis-ndisregisterprotocol.md)
 when the driver initialized.

## -remarks

Registered protocol drivers call **NdisDeregisterProtocol** in any of the following circumstances:

- The driver already called **NdisRegisterProtocol** successfully but it cannot bind to any underlying NDIS driver in the machine.

- The driver is being unloaded. That is, the Unload routine set up in its driver object during initialization has been called or the [**ProtocolUnbindAdapter**](https://msdn.microsoft.com/library/ff563260\(v=vs.85\)) function has been called to release the driver's last remaining binding.

  For more information about the Unload routine and other standard kernel-mode driver routines, see [Kernel-Mode Driver Components](https://msdn.microsoft.com/library/Ff553213).

- The system is being shut down. Because the driver, which is a highest-level protocol, called [**IoRegisterShutdownNotification**](https://msdn.microsoft.com/library/Ff549541) when it initialized, its Shutdown routine has been called.

   See [**IoRegisterShutdownNotification**](https://msdn.microsoft.com/library/Ff549541) for more information.

If a protocol has any open bindings, its call to **NdisDeregisterProtocol** causes NDIS to call the protocol's *ProtocolUnbindAdapter* function once for each open binding. *ProtocolUnbindAdapter* calls **NdisCloseAdapter** to close the binding.

When outstanding opens, if any, have been closed, **NdisDeregisterProtocol** releases all filters its caller has set up and frees the memory NDIS allocated to track bindings and filters for the protocol driver.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Target platform</p></td>
<td><a href="https://go.microsoft.com/fwlink/p/?linkid=531356">Universal</a></td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff561743"><strong>NdisDeregisterProtocolDriver</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Ndis.h (include Ndis.h)</td>
</tr>
<tr class="even">
<td><p>Library</p></td>
<td>Ndis.lib</td>
</tr>
<tr class="odd">
<td><p>IRQL</p></td>
<td><p>PASSIVE_LEVEL</p></td>
</tr>
</tbody>
</table>

## -see-also

- [**NdisCloseAdapter**](nf-ndis-ndiscloseadapter.md)
- [**NdisIMDeInitializeDeviceInstance**](https://msdn.microsoft.com/library/Ff562721)
- [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md)
- [**NdisRegisterProtocol**](nf-ndis-ndisregisterprotocol.md)
- [**ProtocolCloseAdapterComplete**](https://msdn.microsoft.com/library/ff562502\(v=vs.85\).md)
- [**ProtocolStatus**](https://msdn.microsoft.com/library/ff563257\(v=vs.85\).md)
- [**ProtocolUnbindAdapter**](https://msdn.microsoft.com/library/ff563260\(v=vs.85\).md)
