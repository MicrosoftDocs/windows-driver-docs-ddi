---
UID: NF:ndis.NdisOpenAdapter
tech.root: 
title: NdisOpenAdapter
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
 - NdisOpenAdapter
f1_keywords:
 - NdisOpenAdapter
 - ndis/NdisOpenAdapter
dev_langs:
 - c++
helpviewer_keywords:
 - NdisOpenAdapter
---

# NdisOpenAdapter function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisOpenAdapter** sets up a binding between the calling protocol and a particular underlying NIC driver or NDIS intermediate driver.

## -parameters

### -param Status [out]

Pointer to a caller-supplied variable that can be one of the following values on return from this function:

- STATUS\_SUCCESS  
  The requested binding is now set up so the caller can use the values returned at *NdisBindingHandle* and *SelectedMediumIndex* in subsequent calls to *NdisXxx*.

- NDIS\_STATUS\_PENDING  
  The requested operation is being handled asynchronously, and the caller's [**ProtocolOpenAdapterComplete**](https://msdn.microsoft.com/library/ff563238\(v=vs.85\)) function will be called when the open is completed.

- NDIS\_STATUS\_RESOURCES  
  The requested operation failed because NDIS could not allocate sufficient memory or initialize state it uses to track an open binding.

- NDIS\_STATUS\_ADAPTER\_NOT\_FOUND  
  The requested operation failed because the name at *AdapterName* could not be found in the system object namespace.

- NDIS\_STATUS\_UNSUPPORTED\_MEDIA  
  The array at *MediumArray* did not specify any medium that is supported by NDIS or by the underlying driver.

- NDIS\_STATUS\_CLOSING  
  Either the caller or the physical or virtual device designated at *AdapterName* is being closed.

- NDIS\_STATUS\_OPEN\_FAILED  
  The open attempt failed for none of the preceding specific reasons. For example, possibly NDIS could not initialize the filter package for the selected medium.

### -param OpenErrorStatus [out]

Pointer to a caller-supplied variable that can contain an NDIS\_STATUS\_*XXX* error supplying more information if **NdisOpenAdapter** returns an error at *Status*. For example, the driver of a Token Ring NIC might return a ring error in this variable.

### -param NdisBindingHandle [out]

Pointer to a caller-supplied variable in which NDIS returns a handle representing a successful binding between the caller and the given physical or virtual NIC specified at *AdapterName*.

### -param SelectedMediumIndex [out]

Pointer to a caller-supplied variable in which NDIS returns the index of the array element that specifies the type of media the underlying NDIS driver uses.

### -param MediumArray [in]

Pointer to an array of NDIS\_MEDIUM-type values specifying the types of media the caller can support. Possible elements include any proper subset of the following:

- **NdisMedium802\_3**  
  Specifies an Ethernet (802.3) network.

- **NdisMedium802\_5**  
  Specifies a Token Ring (802.5) network.

- **NdisMediumFddi**  
  Specifies a Fiber Distributed Data Interface (FDDI) network.

- **NdisMediumWan**  
  Specifies a wide area network. This type covers various forms of point-to-point and WAN NICs, as well as variant address/header formats that must be negotiated between the protocol driver and the underlying driver after the binding is established.

- **NdisMediumLocalTalk**  
  Specifies a LocalTalk network.

- **NdisMediumDix**  
  Specifies an Ethernet network for which the drivers use the DIX Ethernet header format.

- **NdisMediumArcnetRaw**  
  Specifies an ARCNET network.

- **NdisMediumArcnet878\_2**  
  Specifies an ARCNET (878.2) network.

- **NdisMediumAtm**  
  Specifies an ATM network. Connection-oriented client protocols can bind themselves to an underlying miniport driver that returns this value. Otherwise, legacy protocols bind themselves to the system-supplied LanE intermediate driver, which reports its medium type as either of **NdisMedium802\_3** or **NdisMedium802\_5**, depending on how the LanE driver is configured by the network administrator.

- **NdisMediumWirelessWan**  
  Specifies a wireless network. NDIS 5.X miniport drivers that support wireless LAN (WLAN) or wireless WAN (WWAN) packets declare their medium as **NdisMedium802\_3** and emulate Ethernet to higher-level NDIS drivers.

  **Note**   This media type is not available for use beginning with Windows Vista.

- **NdisMediumIrda**  
  Specifies an infrared (IrDA) network.

- **NdisMediumCoWan**  
  Specifies a wide area network in a connection-oriented environment.

- **NdisMedium1394**  
  Specifies an IEEE 1394 (fire wire) network.

### -param MediumArraySize [in]

Specifies the number of elements at *MediumArray*.

### -param NdisProtocolHandle [in]

Specifies the handle returned by **NdisRegisterProtocol**.

### -param ProtocolBindingContext [in]

Specifies the handle for a caller-supplied resident context area in which the protocol maintains state about this binding after it has been established.

### -param AdapterName [in]

Pointer to an NDIS\_STRING type containing a counted string, specified in the system-default character set, naming the NIC or the virtual adapter of an underlying NDIS driver. This driver exports a set of upper-edge ( *MiniportXxx*) functions. For Windows 2000 and later drivers, this counted string contains Unicode characters. That is, for Windows 2000 and later, NDIS defines the NDIS\_STRING type as a [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879) type.

### -param OpenOptions [in]

Specifies a bitmask containing flags the caller passes to the next-lower driver, assumed to be a NIC driver. Currently, this parameter is reserved for system use.

### -param AddressingInformation [in, optional]

Pointer to an optional variable-length counted string containing information specific to the underlying NIC that the NIC driver can use to program the netcard. This pointer can be **NULL**.

If it is supplied, the addressing information must remain valid until the open operation completes. An underlying NIC driver that supports an asynchronous modem can use this information for dialing.

## -remarks

A protocol driver calls **NdisOpenAdapter** from its [**ProtocolBindAdapter**](https://msdn.microsoft.com/library/ff562465\(v=vs.85\)) function. NDIS no longer supports calling **NdisOpenAdapter** from the **DriverEntry** function, which was an option available to legacy (V3.0) protocols. NDIS no longer supports V3.0 protocols. NDIS fails any attempt to call **NdisOpenAdapter** outside the context of *ProtocolBindAdapter*.

The string at *AdapterName* remains valid only until **NdisOpenAdapter** returns control, even if it returns NDIS\_STATUS\_PENDING at *Status*.

The variables at *NdisBindingHandle* and *SelectedMediumIndex* should be ignored until the [**ProtocolOpenAdapterComplete**](https://msdn.microsoft.com/library/ff563238\(v=vs.85\)) function is called if **NdisOpenAdapter** returns NDIS\_STATUS\_PENDING. Because these variables can remain invalid until *ProtocolOpenAdapterComplete* is called, they cannot be on the stack. Usually, these variables reside in the *ProtocolBindingContext* area since this handle is an input parameter to *ProtocolOpenAdapterComplete*.

A protocol driver should keep the handle returned at *NdisProtocolHandle*. It is a required parameter to other *NdisXxx* functions that the driver calls subsequently. The supplied *ProtocolBindingContext* is an input parameter to the caller's *ProtocolXxx* functions, so protocols usually pass an *NdisProtocolHandle* pointer to a variable somewhere in the caller-allocated context area in their calls to **NdisOpenAdapter**.

The caller uses the value returned at *SelectedMediumIndex* in subsequent calls to [**NdisRequest**](nf-ndis-ndisrequest.md) and/or [**NdisCoRequest**](https://msdn.microsoft.com/library/ff551877\(v=vs.85\)). The OIDs it sets in the request packet depend on the returned *NdisMediumXxx*. For example, if **NdisMediumAtm** is returned at *SelectedMediumIndex*, the protocol driver calls **NdisCoRequest** when specifying OID\_ATM\_ *XXX* or OID\_CO\_*XXX* codes, and **NdisRequest** when specifying OID\_GEN\_*XXX* codes.

If **NdisMediumWan** is returned at *SelectedMediumIndex*, the protocol driver calls **NdisRequest** specifying [OID\_WAN\_MEDIUM\_SUBTYPE](https://msdn.microsoft.com/library/ff561216\(v=vs.85\)) in a query to determine which of the WAN media types the underlying driver uses.

If a previously issued global query of OID\_NETWORK\_TYPE for wireless media indicates that the driver and underlying NIC support more than one **NdisMediumWirelessWan**-type medium, the protocol must select one of the supported media as soon as NDIS has set up the binding and before the protocol selects the header format.

For more information about the general and medium-specific OIDs that protocol drivers use to negotiate with a just-bound NDIS driver, see [NDIS Object Identifiers](https://msdn.microsoft.com/library/ff557081\(v=vs.85\)).

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563715"><strong>NdisOpenAdapterEx</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**ANSI\_STRING**](https://msdn.microsoft.com/library/Ff540605)
- [**DriverEntry of NDIS Protocol Drivers**](https://msdn.microsoft.com/library/Ff548821)
- [**MiniportInitialize**](https://msdn.microsoft.com/library/ff550472\(v=vs.85\))
- [**MiniportQueryInformation**](https://msdn.microsoft.com/library/ff550490\(v=vs.85\))
- [**MiniportSendPackets**](https://msdn.microsoft.com/library/ff550524\(v=vs.85\))
- [**MiniportSetInformation**](https://msdn.microsoft.com/library/ff550530\(v=vs.85\))
- [**NdisCloseAdapter**](nf-ndis-ndiscloseadapter.md)
- [**NdisClOpenAddressFamily**](https://msdn.microsoft.com/library/ff550895\(v=vs.85\))
- [**NdisCoRequest**](https://msdn.microsoft.com/library/ff551877\(v=vs.85\))
- [**NdisCmRegisterAddressFamily**](https://msdn.microsoft.com/library/ff551006\(v=vs.85\))
- [**NdisIMInitializeDeviceInstance**](https://msdn.microsoft.com/library/ff552161\(v=vs.85\))
- [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md)
- [**NdisMIndicateReceivePacket**](https://msdn.microsoft.com/library/ff553533\(v=vs.85\))
- [**NDIS\_PACKET\_OOB\_DATA**](https://msdn.microsoft.com/library/ff557105\(v=vs.85\))
- [**NdisRegisterProtocol**](nf-ndis-ndisregisterprotocol.md)
- [**NdisRequest**](nf-ndis-ndisrequest.md)
- [**NdisSendPackets**](https://msdn.microsoft.com/library/ff554715\(v=vs.85\))
- [**ProtocolBindAdapter**](https://msdn.microsoft.com/library/ff562465\(v=vs.85\))
- [**ProtocolOpenAdapterComplete**](https://msdn.microsoft.com/library/ff563238\(v=vs.85\))
- [**ProtocolReceivePacket**](https://msdn.microsoft.com/library/ff563251\(v=vs.85\))
- [**UNICODE\_STRING**](https://msdn.microsoft.com/library/Ff564879)
