---
UID: NF:ndis.NdisRegisterProtocol
tech.root: 
title: NdisRegisterProtocol
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
 - NdisRegisterProtocol
f1_keywords:
 - NdisRegisterProtocol
 - ndis/NdisRegisterProtocol
dev_langs:
 - c++
helpviewer_keywords:
 - NdisRegisterProtocol
---

# NdisRegisterProtocol function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisRegisterProtocol** registers an NDIS driver's *ProtocolXxx* entry points and name with the NDIS library when the driver initializes.

## -parameters

### -param Status [out]

Pointer to a caller-supplied variable that can be one of the following values on return from this function:

- NDIS\_STATUS\_SUCCESS  
  The NDIS library registered the caller as a protocol driver.

- NDIS\_STATUS\_BAD\_CHARACTERISTICS  
  The *CharacteristicsLength* is too small for the **MajorNdisVersion** specified in the buffer at *ProtocolCharacteristics*.

- NDIS\_STATUS\_BAD\_VERSION  
  The **MajorNdisVersion** specified in the buffer at *ProtocolCharacteristics* is invalid.

- NDIS\_STATUS\_RESOURCES  
  A shortage of resources, possibly memory, prevented the NDIS library from registering the caller.

### -param NdisProtocolHandle [out]

Pointer to a caller-supplied variable in which this function returns a handle representing the registered driver.

### -param ProtocolCharacteristics [in]

Pointer to an NDIS\_PROTOCOL\_CHARACTERISTICS structure set up by the caller. The structure at *ProtocolCharacteristics* is defined as follows:

```cpp
        typedef struct _NDIS_PROTOCOL_CHARACTERISTICS {
            UCHAR MajorNdisVersion;
            UCHAR MinorNdisVersion;
            UINT Reserved;
            OPEN_ADAPTER_COMPLETE_HANDLER OpenAdapterCompleteHandler;
            CLOSE_ADAPTER_COMPLETE_HANDLER CloseAdapterCompleteHandler;
            SEND_COMPLETE_HANDLER SendCompleteHandler;
            TRANSFER_DATA_COMPLETE_HANDLER TransferDataCompleteHandler;
            RESET_COMPLETE_HANDLER ResetCompleteHandler;
            REQUEST_COMPLETE_HANDLER RequestCompleteHandler;
            RECEIVE_HANDLER ReceiveHandler;
            RECEIVE_COMPLETE_HANDLER ReceiveCompleteHandler;
            STATUS_HANDLER StatusHandler;
            STATUS_COMPLETE_HANDLER StatusCompleteHandler;
            NDIS_STRING Name;
        //
        // MajorNdisVersion must be set to 0x04 or 0x05
        // with any of the following members.
        //
            RECEIVE_PACKET_HANDLER ReceivePacketHandler;
            BIND_HANDLER BindAdapterHandler;
            UNBIND_HANDLER UnbindAdapterHandler;
            PNP_EVENT_HANDLER PnPEventHandler;
            UNLOAD_PROTOCOL_HANDLER UnloadHandler;
        //
        // MajorNdisVersion must be set to 0x05 
        // with any of the following members.
        //
            CO_SEND_COMPLETE_HANDLER CoSendCompleteHandler;
            CO_STATUS_HANDLER CoStatusHandler;
            CO_RECEIVE_PACKET_HANDLER CoReceivePacketHandler;
            CO_AF_REGISTER_NOTIFY_HANDLER CoAfRegisterNotifyHandler;
        } NDIS_PROTOCOL_CHARACTERISTICS, *PNDIS_PROTOCOL_CHARACTERISTICS;
```

The driver should initialize this structure with zeros before setting up the following members:

- **MajorNdisVersion**  
  Specifies the major version of the NDIS library the driver is using. The current value is 0x05, although the NDIS library continues to support existing drivers developed for NDIS V4.0. NDIS no longer supports V3.0 protocols.

- **MinorNdisVersion**  
  Specifies the minor NDIS version. The current value is 0x00.

- **Reserved**  
  This member is reserved for system use.

- **OpenAdapterCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolOpenAdapterComplete**](ff563238\(v=vs.85\).md) function.

- **CloseAdapterCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolCloseAdapterComplete**](ff562502\(v=vs.85\).md) function.

- **SendCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolSendComplete**](ff563256\(v=vs.85\).md) function, if any.

- **TransferDataCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolTransferDataComplete**](ff563259\(v=vs.85\).md) function, if any.

- **ResetCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolResetComplete**](ff563255\(v=vs.85\).md) function.

- **RequestCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolRequestComplete**](ff563254\(v=vs.85\).md) function.

- **ReceiveHandler**  
  Specifies the entry point of the caller's [**ProtocolReceive**](ff563246\(v=vs.85\).md) function, if any.

- **ReceiveCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolReceiveComplete**](ff563249\(v=vs.85\).md) function.

- **StatusHandler**  
  Specifies the entry point of the caller's [**ProtocolStatus**](ff563257\(v=vs.85\).md) function, if any.

- **StatusCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolStatusComplete**](ff563258\(v=vs.85\).md) function.

- **Name**  
  An NDIS\_STRING type containing a caller-initialized counted string, in the system-default character set, naming the driver. For Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and later, NDIS defines the NDIS\_STRING type as a [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879) type. This string must match that specified in the registry (under *Services*) when the protocol was installed.

  **NdisRegisterProtocol** converts the supplied string to upper case, so a protocol driver writer cannot assume that changing the case of an already registered protocol name creates a unique name for the driver.

- **ReceivePacketHandler**  
  Specifies the entry point of the caller's [**ProtocolReceivePacket**](ff563251\(v=vs.85\).md) function, if any, or **NULL**. Protocols that bind to any NIC driver that supports multipacket receive indications should supply a *ProtocolReceivePacket* function to enhance their performance. However, a protocol that binds itself exclusively to connection-oriented miniports also can set this member to **NULL**.

- **BindAdapterHandler**  
  Specifies the entry point of the caller's [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md) function. Callers that set the value in the **MajorNdisVersion** member to 0x05 or 0x04 must supply a *ProtocolBindAdapter* function and support Plug and Play. NDIS intermediate drivers also must supply a *ProtocolBindAdapter* function, which allows those intermediate drivers to call [**NdisIMRegisterLayeredMiniport**](ff552205\(v=vs.85\).md) and to defer full driver initialization until underlying NIC drivers have initialized.

- **UnbindAdapterHandler**  
  Specifies the entry point of the caller's [**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md) function. NDIS drivers that supply a *ProtocolBindAdapter* function also must supply a *ProtocolUnbindAdapter* function.

- **PnPEventHandler**  
  Specifies the entry point of the caller's [**ProtocolPnPEvent**](ff563243\(v=vs.85\).md) function, if any.

- **UnloadHandler**  
  Specifies the entry point of the caller's **ProtocolUnbind** function, if any, or **NULL**.

- **CoSendCompleteHandler**  
  Specifies the entry point of the caller's [**ProtocolCoSendComplete**](ff563230\(v=vs.85\).md) function, which a connection-oriented client or call manager must supply. A connection-oriented client supplies a [**ProtocolSendComplete**](ff563256\(v=vs.85\).md) function if it also binds itself to connectionless miniports.

- **CoStatusHandlerCoStatusHandler**  
  Specifies the entry point of the caller's [**ProtocolCoStatus**](ff563235\(v=vs.85\).md) function, which a connection-oriented client or call manager must supply. A connection-oriented client supplies a [**ProtocolStatus**](ff563257\(v=vs.85\).md) function if it also binds itself to connectionless miniports.

- **CoReceivePacketHandler**  
  Specifies the entry point of the caller's [**ProtocolCoReceivePacket**](ff563224\(v=vs.85\).md) function, which a connection-oriented client or call manager must supply. A connection-oriented client supplies a [**ProtocolReceivePacket**](ff563251\(v=vs.85\).md) function and/or [**ProtocolReceive**](ff563246\(v=vs.85\).md) and [**ProtocolTransferDataComplete**](ff563259\(v=vs.85\).md) functions if it also binds itself to connectionless miniports.

- **CoAfRegisterNotifyHandler**  
  Specifies the entry point of the caller's **ProtocolAfRegisterNotify** function, which a connection-oriented client must supply.

### -param CharacteristicsLength [in]

Specifies the size in bytes of the structure at *ProtocolCharacteristics*. If the build directive -DNDIS50=1 or -DNDIS40=1 is specified in the *sources* file ahead of **\#include***Ndis.h* , the sizeof(NDIS\_PROTOCOL\_CHARACTERISTICS) is automatically set to the appropriate value. If neither directive is specified, NDIS assumes the V3.0 characteristics structure is being used.

The values set in the **MajorNdisVersion** and **MinorNdisVersion** members of the characteristics structure must be consistent with the build directive, or they must be 0x03 and 0x00, respectively.

## -remarks

A protocol driver must specify an **MajorNdisVersion** of 0x05 (the current version) or 0x04. NDIS no longer supports V.30 protocols and therefore does not load a protocol that specifies an **MajorNdisVersion** of 0x03.

All protocols must be Plug and Play (PnP) capable. A protocol must therefore specify entry points for **BindAdapterHandler** and **UnbindAdapterHandler**. NDIS does not load a protocol that specifies **NULL** for these handlers.

For the best possible performance, any protocol that will layer itself above a connectionless NIC driver that supports multipacket receives should provide a [**ProtocolReceivePacket**](ff563251\(v=vs.85\).md) function. Such a protocol driver also must provide a *ProtocolReceive* function. Any connectionless NIC driver that supports multipacket sends is also likely to indicate multipacket receives.

All connection-oriented protocols, whether clients or call managers, must register a [**ProtocolCoReceivePacket**](ff563224\(v=vs.85\).md) function. Client protocols that also bind themselves to connectionless NIC drivers provide *ProtocolReceivePacket* and [**ProtocolReceive**](ff563246\(v=vs.85\).md) functions as well. Connection-oriented protocols must register additional connection-oriented entry points with NDIS by calling either [**NdisClOpenAddressFamily**](ff550895\(v=vs.85\).md) for clients or [**NdisCmRegisterAddressFamily**](ff551006\(v=vs.85\).md) for call managers from their *ProtocolBindAdapter* functions.

After a successful call to **NdisRegisterProtocol**, a driver cannot alter the set of *ProtocolXxx* functions it supplied.

A successfully registered driver should save the handle returned at *NdisProtocolHandle*. It is a required parameter to other *NdisXxx* functions that the driver calls subsequently.

After a successful call to **NdisRegisterProtocol**, the **DriverEntry** function of a PnP-aware or connection-oriented protocol returns control because such a driver's *ProtocolBindAdapter* function will be called subsequently one or more times to set up bindings to underlying NIC(s). Otherwise, the protocol driver can call [**NdisOpenAdapter**](ff553673\(v=vs.85\).md) to set up a binding to the underlying NIC driver or to layer itself above any NDIS driver that registered a set of NDIS *MiniportXxx* functions.

## Requirements

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff564520"><strong>NdisRegisterProtocolDriver</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**ANSI\_STRING**](https://msdn.microsoft.com/library/Ff540605)
- [**DriverEntry of NDIS Protocol Drivers**](https://msdn.microsoft.com/library/Ff548821)
- [**NdisClOpenAddressFamily**](ff550895\(v=vs.85\).md)
- [**NdisCmRegisterAddressFamily**](ff551006\(v=vs.85\).md)
- [**NdisDeregisterProtocol**](ff551909\(v=vs.85\).md)
- [**NdisIMRegisterLayeredMiniport**](ff552205\(v=vs.85\).md)
- [**NdisInitializeString**](https://msdn.microsoft.com/library/Ff562741)
- [**NdisInitUnicodeString**](https://msdn.microsoft.com/library/Ff562745)
- [**NdisMCmRegisterAddressFamily**](ff553429\(v=vs.85\).md)
- [**NdisOpenAdapter**](ff553673\(v=vs.85\).md)
- [**NdisZeroMemory**](https://msdn.microsoft.com/library/Ff564698)
- [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md)
- [**ProtocolCloseAdapterComplete**](ff562502\(v=vs.85\).md)
- [**ProtocolCoAfRegisterNotify**](https://msdn.microsoft.com/library/Ff570251)
- [**ProtocolCoReceivePacket**](ff563224\(v=vs.85\).md)
- [**ProtocolCoSendComplete**](ff563230\(v=vs.85\).md)
- [**ProtocolCoStatus**](ff563235\(v=vs.85\).md)
- [**ProtocolOpenAdapterComplete**](ff563238\(v=vs.85\).md)
- [**ProtocolPnPEvent**](ff563243\(v=vs.85\).md)
- [**ProtocolReceive**](ff563246\(v=vs.85\).md)
- [**ProtocolReceiveComplete**](ff563249\(v=vs.85\).md)
- [**ProtocolReceivePacket**](ff563251\(v=vs.85\).md)
- [**ProtocolRequestComplete**](ff563254\(v=vs.85\).md)
- [**ProtocolResetComplete**](ff563255\(v=vs.85\).md)
- [**ProtocolSendComplete**](ff563256\(v=vs.85\).md)
- [**ProtocolStatus**](ff563257\(v=vs.85\).md)
- [**ProtocolStatusComplete**](ff563258\(v=vs.85\).md)
- [**ProtocolTransferDataComplete**](ff563259\(v=vs.85\).md)
- [**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md)
- [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879)
