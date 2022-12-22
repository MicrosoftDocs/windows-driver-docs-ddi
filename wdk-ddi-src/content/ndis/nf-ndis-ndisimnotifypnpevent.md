---
UID: NF:ndis.NdisIMNotifyPnPEvent
tech.root: 
title: NdisIMNotifyPnPEvent
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
 - NdisIMNotifyPnPEvent
f1_keywords:
 - NdisIMNotifyPnPEvent
 - ndis/NdisIMNotifyPnPEvent
dev_langs:
 - c++
helpviewer_keywords:
 - NdisIMNotifyPnPEvent
---

# NdisIMNotifyPnPEvent function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisIMNotifyPnPEvent** propagates notification of a Plug and Play or Power Management event to an overlying driver.

## -parameters

### -param MiniportHandle [in]

The handle input to [**MiniportInitialize**](https://msdn.microsoft.com/library/ff550472\(v=vs.85\)). This handle represents the miniport driver affected by the Plug and Play or Power Management event passed to the caller's [**ProtocolPnPEvent**](ff563243\(v=vs.85\)) function.

### -param NetPnPEvent [in]

Pointer to a NET\_PNP\_EVENT structure, which describes the Plug and Play event or Power Management event being indicated to the protocol driver.

## -returns

**NdisIMNotifyPnPEvent** can return either of the following:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Return code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>NDIS_STATUS_SUCCESS</strong></td>
<td><p>The overlying driver succeeded propagated Plug and Play event was succeeded.</p></td>
</tr>
<tr class="even">
<td><strong>NDIS_STATUS_FAILURE</strong></td>
<td><p>The overlying driver failed the propagated Plug and Play event.</p></td>
</tr>
</tbody>
</table>

The return value is significant only when the propagated event is a **NetEventQueryPower** or a **NetEventQueryRemove**. For all other propagated events, the return value is always NDIS\_STATUS\_SUCCESS.

## -remarks

An NDIS intermediate driver calls **NdisIMNotifyPnPEvent** in the context of the driver's [**ProtocolPnPEvent**](https://msdn.microsoft.com/library/ff563243\(v=vs.85\)) function to propagate notification of a Plug and Play or Power Management event to the overlying driver.

If the propagated event is a **NetEventQueryPower** or a **NetEventQueryRemove**, the intermediate driver must check the NDIS\_STATUS value returned by **NdisIMNotifyPnPEvent**. If the returned status is NDIS\_STATUS\_SUCCESS, the intermediate driver should handle the event internally as usual and then return NDIS\_STATUS\_SUCCESS from its *ProtocolPnPEvent* function. If the returned status is NDIS\_STATUS\_FAILURE, the intermediate driver should return NDIS\_STATUS\_FAILURE from its *ProtocolPnPEvent* without further processing.

For all other propagated events, **NdisIMNotifyPnPEvent** always returns NDIS\_STATUS\_SUCCESS. The intermediate driver's *ProtocolPnPEvent* function in such cases should propagate the NDIS\_STATUS returned by **NdisIMNotifyPnPEvent**.

How the intermediate driver processes a **NetEventSetPower** received by its *ProtocolPnPEvent* function depends on the specified device power state. If the specified device power state is **NdisDeviceStateD0**, the intermediate driver should handle the event internally as usual and then call **NdisIMNotifyPnPEvent**. For any other specified device power state, the intermediate driver should first call **NdisIMNotifyPnPEvent** and then handle the event internally as usual.

An intermediate driver should call **NdisIMNotifyPnPEvent** to propagate a **NetEventReconfigure** or **NetEventBindList** only if the **NetEventReconfigure** or **NetEventBindList** is indicated on a non-**NULL***ProtocolBindingContext*. If a **NetEventReconfigure** or **NetEventBindList** is indicated on a **NULL***ProtocolBindingContext*, the intermediate driver should not call **NdisIMNotifyPnPEvent** to propagate the event.

If an intermediate driver handles a **NetEventReconfigure** or a **NetEventBindList**, it should validate any data associated with the event. (For more information about such data, see [**NET\_PNP\_EVENT for Protocol Drivers**](https://msdn.microsoft.com/library/Ff568751).)

System support for **NdisIMNotifyPnPEvent** is available in Windows XP and later versions.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563616"><strong>NdisMNetPnPEvent</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**NET\_PNP\_EVENT**](https://msdn.microsoft.com/library/Ff568751)
- [**ProtocolPnPEvent**](https://msdn.microsoft.com/library/ff563243\(v=vs.85\))
