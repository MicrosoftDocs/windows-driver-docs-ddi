---
UID: NF:ndis.NdisIMRegisterLayeredMiniport
tech.root: 
title: NdisIMRegisterLayeredMiniport
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
 - NdisIMRegisterLayeredMiniport
f1_keywords:
 - NdisIMRegisterLayeredMiniport
 - ndis/NdisIMRegisterLayeredMiniport
dev_langs:
 - c++
helpviewer_keywords:
 - NdisIMRegisterLayeredMiniport
---
# NdisIMRegisterLayeredMiniport function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisIMRegisterLayeredMiniport** registers an intermediate driver's *MiniportXxx* entry points and name with the NDIS library when the driver initializes.

## -parameters

### -param NdisWrapperHandle [in]

Specifies the handle returned by [**NdisMInitializeWrapper**](ff553547\(v=vs.85\).md).

### -param MiniportCharacteristics [in]

Pointer to an NDIS *XX*\_MINIPORT\_CHARACTERISTICS structure set up by the caller. The structure at *MiniportCharacteristics* is defined as follows:

```cpp
        typedef struct _NDIS_MINIPORT_CHARACTERISTICS {
            UCHAR MajorNdisVersion;
            UCHAR MinorNdisVersion;
            UINT Reserved;
            W_CHECK_FOR_HANG_HANDLER CheckForHangHandler;
            W_DISABLE_INTERRUPT_HANDLER DisableInterruptHandler;
            W_ENABLE_INTERRUPT_HANDLER  EnableInterruptHandler;
            W_HALT_HANDLER HaltHandler;
            W_HANDLE_INTERRUPT_HANDLER  HandleInterruptHandler;
            W_INITIALIZE_HANDLER InitializeHandler;
            W_ISR_HANDLER ISRHandler;
            W_QUERY_INFORMATION_HANDLER QueryInformationHandler;
            W_RECONFIGURE_HANDLER ReconfigureHandler;
            W_RESET_HANDLER ResetHandler;
            W_SEND_HANDLER SendHandler; 
            W_SET_INFORMATION_HANDLER SetInformationHandler;
            W_TRANSFER_DATA_HANDLER TransferDataHandler;
        //
        // Version used is V4.0 or V5.0
        // with following members
        //
            W_RETURN_PACKET_HANDLER ReturnPacketHandler;
            W_SEND_PACKETS_HANDLER SendPacketsHandler;
            W_ALLOCATE_COMPLETE_HANDLER AllocateCompleteHandler;
        //
        // Version used is V5.0 with the following members
        //
            W_CO_CREATE_VC_HANDLER CoCreateVcHandler;
            W_CO_DELETE_VC_HANDLER CoDeleteVcHandler;
            W_CO_ACTIVATE_VC_HANDLER CoActivateVcHandler;
            W_CO_DEACTIVATE_VC_HANDLER CoDeactivateVcHandler;
            W_CO_SEND_PACKETS_HANDLER CoSendPacketsHandler;
            W_CO_REQUEST_HANDLER CoRequestHandler;
        //
        // Version used is V5.1 with the following members
        //
            W_CANCEL_SEND_PACKETS_HANDLER CancelSendPacketsHandler;
            W_MINIPORT_PNPEVENTNOTIFY_HANDLER PnPEventNotifyHandler;
            W_MINIPORT_SHUTDOWN_HANDLER AdapterShutdownHandler;
        } NDIS_MINIPORT_CHARACTERISTICS, *PNDIS_MINIPORT_CHARACTERISTICS;
```

An NDIS intermediate driver should initialize this structure with zeros before setting up any of the following members:

- **MajorNdisVersion**  
  Specifies the major version of the NDIS library the driver is using. The current value is 0x05, although the NDIS library continues to support existing miniport drivers developed for NDIS 4.0.

- **MinorNdisVersion**  
  Specifies the minor version of the NDIS library the driver is using. The current value is 0x00, although NDIS continues to support existing drivers.

- **Reserved**  
  This member is reserved for system use.

- **CheckForHangHandler**  
  Specifies the entry point of the caller's [**MiniportCheckForHang**](ff549367\(v=vs.85\).md) function, if any, or **NULL**.

- **DisableInterruptHandler**  
  Specifies **NULL**.

- **EnableInterruptHandler**  
  Specifies **NULL**.

- **HaltHandler**  
  Specifies the entry point of the caller's [**MiniportHalt**](ff549451\(v=vs.85\).md) function.

- **HandleInterruptHandler**  
  Specifies **NULL**.

- **InitializeHandler**  
  Specifies the entry point of the caller's [**MiniportInitialize**](ff550472\(v=vs.85\).md) function.

- **ISRHandler**  
  Specifies **NULL**.

- **QueryInformationHandler**  
  Specifies the entry point of the caller's [**MiniportQueryInformation**](ff550490\(v=vs.85\).md) function.

- **ReconfigureHandler**  
  Specifies **NULL**.

- **ResetHandler**  
  Specifies the entry point of the caller's [*MiniportReset*](ff550502\(v=vs.85\).md) function.

- **SendHandler**  
  Specifies the entry point of the caller's [**MiniportSend**](ff550518\(v=vs.85\).md) function, [**MiniportWanSend**](ff550561\(v=vs.85\).md) function, or **NULL** if the caller supplies a [**MiniportSendPackets**](ff550524\(v=vs.85\).md) function.

  If the driver supports multipacket sends or media-specific information, it sets the **SendPacketsHandler** member instead and sets this member to **NULL**.

- **SetInformationHandler**
  Specifies the entry point of the caller's [**MiniportSetInformation**](ff550530\(v=vs.85\).md) function.

- **TransferDataHandler**  
  Specifies the entry point of the caller's [**MiniportTransferData**](ff550556\(v=vs.85\).md) function, if any, or **NULL**. This miniport driver function is required unless the caller is the driver of a WAN NIC or the caller supports multipacket receives and, therefore, supplies the entry point of its [**MiniportReturnPacket**](ff550510\(v=vs.85\).md) function at **ReturnPacketHandler**.

- **ReturnPacketHandler**  
  Specifies the entry point of the caller's *MiniportReturnPacket* function, if any, or **NULL**.

- **SendPacketsHandler**  
  Specifies the entry point of the caller's *MiniportSendPackets* function, if any, or **NULL**.

- **AllocateCompleteHandler**  
  Specifies **NULL**.

- **CoCreateVcHandler**  
  Specifies **NULL**.

- **CoDeleteVcHandler**  
  Specifies **NULL**.

- **CoActivateVcHandler**  
  Specifies **NULL**.

- **CoDeactivateVcHandler**  
  Specifies **NULL**.

- **CoSendPacketsHandler**  
  Specifies **NULL**.

- **CoRequestHandler**  
  Specifies **NULL**.

- **CancelSendPacketsHandler**  
  Specifies the entry point of the caller's [**MiniportCancelSendPackets**](ff549359\(v=vs.85\).md) function, if any, or **NULL**. Intermediate drivers that queue send packets for more than one second should register a *MiniportCancelSendPackets* function.

- **PnPEventNotifyHandler**  
  Specifies the entry point of the caller's [**MiniportPnPEventNotify**](ff550487\(v=vs.85\).md) function. NDIS 5.1 miniport drivers must register a *MiniportPnPEventNotify* function. Miniport drivers ''that have a WDM lower edge should register a *MiniportPnPEventNotify* function.

- **AdapterShutdownHandler**  
  Specifies the entry point of the caller's [**MiniportShutdown**](ff550533\(v=vs.85\).md) function, if any, or **NULL**. NDIS 5.1 intermediate drivers must register a *MiniportShutdown* function. NDIS 5.1 intermediate drivers should register a *MiniportShutdown* function by calling **NdisIMRegisterLayeredMiniport**--not by calling [**NdisMRegisterAdapterShutdownHandler**](ff553584\(v=vs.85\).md).

### -param CharacteristicsLength [in]

Specifies the length in bytes of the caller-supplied characteristics buffer. Depending on the value of **MajorNdisVersion**, this parameter must be either sizeof(NDIS50\_MINIPORT\_CHARACTERISTICS) if the driver supplies an NDIS50\_MINIPORT\_CHARACTERISTICS structure or sizeof(NDIS40\_MINIPORT\_CHARACTERISTICS) if the driver supplies an NDIS40\_MINIPORT\_CHARACTERISTICS structure.

If the driver includes the build instruction NDIS50\_MINIPORT (or NDIS40\_MINIPORT, as appropriate) in its sources or if the driver writer uses the -NDIS50\_MINIPORT (or ..40..) compiler switch, this parameter is set when the driver is built.

### -param DriverHandle [out]

Pointer to a variable in which **NdisIMRegisterLayeredMiniport**, if this call is successful, returns a handle that the caller should save. The caller subsequently must pass this handle to [**NdisIMInitializeDeviceInstance**](ff552161\(v=vs.85\).md), usually from its [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md) function.

## -returns

**NdisIMRegisterLayeredMiniport** returns NDIS\_STATUS\_SUCCESS if it registered the caller as a miniport driver, or it can return one of the following status values:

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
<td><strong>NDIS_STATUS_BAD_CHARACTERISTICS</strong></td>
<td><p>The <em>CharacteristicsLength</em> is too small for the <strong>MajorNdisVersion</strong> specified in the buffer at <em>MiniportCharacteristics</em>.</p></td>
</tr>
<tr class="even">
<td><strong>NDIS_STATUS_BAD_VERSION</strong></td>
<td><p>The <strong>MajorNdisVersion</strong> or <strong>MajorNdisVersion</strong> specified in the characteristics structure is invalid.</p></td>
</tr>
<tr class="odd">
<td><strong>NDIS_STATUS_RESOURCES</strong></td>
<td><p>A shortage of resources, possibly memory, prevented the NDIS library from registering the caller as a miniport driver.</p></td>
</tr>
<tr class="even">
<td><strong>NDIS_STATUS_FAILURE</strong></td>
<td><p>This is a default error status, returned when none of the preceding errors caused the registration to fail. For example, if the NDIS library cannot load the driver's image and lock it into system memory, it returns this error.</p></td>
</tr>
</tbody>
</table>

## -remarks

Any NDIS intermediate driver that exports both *MiniportXxx* and *ProtocolXxx* functions sets up a characteristics structure and calls **NdisIMRegisterLayeredMiniport** from its **DriverEntry** function after **DriverEntry** calls [**NdisMInitializeWrapper**](ff553547\(v=vs.85\).md). This structure is copied in the **NdisIMRegisterLayeredMiniport** request to the NDIS library's internal storage. Thus, once it has registered, such a driver cannot change its handler functions.

After such an NDIS intermediate driver has called **NdisIMRegisterLayeredMiniport** successfully, it must call [**NdisRegisterProtocol**](ff554653\(v=vs.85\).md) to register its *ProtocolXxx* functions with the NDIS library. Such a driver usually has both [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md) and [**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md) functions. Its *ProtocolBindAdapter* function will be called next when the underlying NIC driver has initialized successfully. *ProtocolBindAdapter* then can establish a binding to that NIC driver with [**NdisOpenAdapter**](ff553673\(v=vs.85\).md).

An NDIS intermediate driver should have a [**MiniportSendPackets**](ff550524\(v=vs.85\).md) function if an underlying NIC driver might support multipacket sends or consume media-specific information, such as packet priorities, sent down in a packet array from a higher-level protocol. An NDIS intermediate driver should have a [**MiniportReturnPacket**](ff550510\(v=vs.85\).md) function if an underlying NIC driver might support multipacket receive indications or indicate packet arrays containing media-specific information. The NDIS library handles packet arrays transferred between an underlying NIC driver and higher-level protocol that support only single-packet transfers on behalf of such an intermediate driver.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563654"><strong>NdisMRegisterMiniportDriver</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**DriverEntry of NDIS Miniport Drivers**](https://msdn.microsoft.com/library/Ff548818)
- [**DriverEntry of NDIS Protocol Drivers**](https://msdn.microsoft.com/library/Ff548821)
- [**MiniportCheckForHang**](ff549367\(v=vs.85\).md)
- [**MiniportHalt**](ff549451\(v=vs.85\).md)
- [**MiniportInitialize**](ff550472\(v=vs.85\).md)
- [**MiniportQueryInformation**](ff550490\(v=vs.85\).md)
- [*MiniportReset*](ff550502\(v=vs.85\).md)
- [**MiniportReturnPacket**](ff550510\(v=vs.85\).md)
- [**MiniportSend**](ff550518\(v=vs.85\).md)
- [**MiniportSendPackets**](ff550524\(v=vs.85\).md)
- [**MiniportSetInformation**](ff550530\(v=vs.85\).md)
- [**MiniportTransferData**](ff550556\(v=vs.85\).md)
- [**MiniportWanSend**](ff550561\(v=vs.85\).md)
- [**NdisIMInitializeDeviceInstance**](ff552161\(v=vs.85\).md)
- [**NdisMRegisterAdapterShutdownHandler**](ff553584\(v=vs.85\).md)
- [**NdisMRegisterMiniport**](ff553602\(v=vs.85\).md)
- [**NdisOpenAdapter**](ff553673\(v=vs.85\).md)
- [**NdisRegisterProtocol**](ff554653\(v=vs.85\).md)
- [**NdisZeroMemory**](https://msdn.microsoft.com/library/Ff564698)
- [**ProtocolBindAdapter**](ff562465\(v=vs.85\).md)
- [**ProtocolReceivePacket**](ff563251\(v=vs.85\).md)
- [**ProtocolUnbindAdapter**](ff563260\(v=vs.85\).md)
