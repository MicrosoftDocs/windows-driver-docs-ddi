---
UID: NF:ndis.NdisCancelSendPackets
tech.root: 
title: NdisCancelSendPackets
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
 - NdisCancelSendPackets
f1_keywords:
 - NdisCancelSendPackets
 - ndis/NdisCancelSendPackets
dev_langs:
 - c++
helpviewer_keywords:
 - NdisCancelSendPackets
---

# NdisCancelSendPackets function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisCancelSendPackets** cancels transmission of all packets marked with the specified cancellation identifier on the miniport driver identified by the binding handle.

## Syntax

```cpp
VOID NdisCancelSendPackets(
  _In_ NDIS_HANDLE NdisBindingHandle,
  _In_ PVOID       CancelId
);
```

## -parameters

### -param NdisBindingHandle [in]

Specifies the handle returned by [**NdisOpenAdapter**](ff553673\(v=vs.85\).md) that identifies the NIC or virtual adapter to which the cancellation applies.

### -param CancelId [in]

Pointer to the cancellation identifier. This identifier specifies the packet or group of packets for which transmission is being canceled.

## Return value

None

## -remarks

Transport protocols map IRPs received from higher-level software to NDIS packets, which the protocols then send to lower-level drivers for transmission. If an IRP is canceled, a transport protocol can call the **NdisCancelSendPackets** function to cancel the pending transmission of the corresponding NDIS packet.

The **NdisCancelSendPackets** function cancels packet transmissions on a single binding. To cancel packet transmissions on more than one binding, a protocol or intermediate driver must call the **NdisCancelSendPackets** function once for each binding.

The protocol or intermediate driver must ensure that *NdisBindingHandle*, which represents the driver's binding to the adapter, remains valid for the duration of the call to **NdisCancelSendPackets**. That is, the protocol or intermediate driver must not call the [**NdisCloseAdapter**](ff550904\(v=vs.85\).md) function to close the binding before **NdisCancelSendPackets** returns.

There is no guarantee that calling **NdisCancelSendPackets** will cancel the pending transmission of all packets with the specified cancellation ID. For example, if the next-lower driver to which the protocol or intermediate driver is bound does not provide a [**MiniportCancelSendPackets**](ff549359\(v=vs.85\).md) function, a call to **NdisCancelSendPackets** does nothing.

In all cases, packets submitted for transmission are returned to the originating protocol or intermediate driver through a call to the driver's [**ProtocolSendComplete**](ff563256\(v=vs.85\).md) or [**ProtocolCoSendComplete**](ff563230\(v=vs.85\).md) function. Canceled send packets are returned with a completion status of NDIS\_STATUS\_ABORTED. The delay between calling **NdisCancelSendPackets** and the return of the canceled packets can vary and therefore cannot be exactly specified.

## Requirements

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
<td><p>Not supported for NDIS 6.0 drivers in Windows Vista. Use NdisCancelSendNetBufferLists instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.</p></td>
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
<td><p>&lt;= DISPATCH_LEVEL.</p></td>
</tr>
</tbody>
</table>

## -see-also

[**MiniportCancelSendPackets**](ff549359\(v=vs.85\).md)

[**NdisGeneratePartialCancelId**](https://msdn.microsoft.com/library/Ff562623)

[**NDIS\_GET\_PACKET\_CANCEL\_ID**](ff556988\(v=vs.85\).md)

[**NDIS\_SET\_PACKET\_CANCEL\_ID**](ff557195\(v=vs.85\).md)

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=documentation%20feedback%20%5Bnetxp\\netxp%5D:%20ndiscancelsendpackets%20function%20%20release:%20\(6/19/2017\)&body=%0a%0aprivacy%20statement%0a%0awe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20we%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20while%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0a%0afor%20more%20info%20about%20microsoft's%20privacy%20policy,%20see%20https://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")
