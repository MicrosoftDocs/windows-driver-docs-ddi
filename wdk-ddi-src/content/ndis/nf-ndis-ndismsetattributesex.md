---
UID: NF:ndis.NdisMSetAttributesEx
tech.root: netvista
title: NdisMSetAttributesEx
ms.date: 01/04/2023
targetos: Windows
description: NdisMSetAttributesEx informs the NDIS library about significant features of the caller's NIC or virtual NIC during initialization.
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
 - NdisMSetAttributesEx
f1_keywords:
 - NdisMSetAttributesEx
 - ndis/NdisMSetAttributesEx
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMSetAttributesEx
---

# NdisMSetAttributesEx function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisMSetAttributesEx** informs the NDIS library about significant features of the caller's NIC or virtual NIC during initialization.

## -parameters

### -param MiniportAdapterHandle [in]

Specifies the handle input to [**MiniportInitialize**](https://msdn.microsoft.com/library/ff550472\(v=vs.85\)).

### -param MiniportAdapterContext [in]

Specifies a handle for a resident context area allocated by *MiniportInitialize*.

### -param CheckForHangTimeInSeconds [in, optional]

Specifies the interval, in seconds, at which NDIS should call the [**MiniportCheckForHang**](https://msdn.microsoft.com/library/ff549367\(v=vs.85\)) function. If a driver has not responded to an OID request or sent request within two successive calls to *MiniportCheckForHang*, NDIS can call the driver's [*MiniportReset*](https://msdn.microsoft.com/library/ff550502\(v=vs.85\)) function.

The actual interval that NDIS uses when calling *MiniportCheckForHang* is always a multiple of 2 seconds. For example, if you specifiy 5 seconds, the actual interval will be approximately 4 seconds.

Specifying zero for this parameter indicates that NDIS should call *MiniportCheckForHang* at the NDIS default 2-second interval.

If the caller sets NDIS\_ATTRIBUTE\_DESERIALIZE in *AttributeFlags*, NDIS does not queue pending sends for the miniport driver. Instead, such a deserialized driver must manage its own queuing of subsequent send requests internally whenever it has insufficient resources to transmit an incoming send immediately.

### -param AttributeFlags [in]

Specifies a bitmask that can be set with one or more (ORed) of the following flags:

- NDIS\_ATTRIBUTE\_BUS\_MASTER  
  Set if the caller's NIC is a bus-master DMA device.

- NDIS\_ATTRIBUTE\_DESERIALIZE  
  Set if the caller is a deserialized miniport driver.

- NDIS\_ATTRIBUTE\_IGNORE\_PACKET\_TIMEOUT  
  Set if NDIS should not attempt to time-out pending send packets that it holds queued to the caller. Intermediate drivers should set this flag, but NIC drivers should not.

- NDIS\_ATTRIBUTE\_IGNORE\_REQUEST\_TIMEOUT  
  Set if NDIS should not attempt to time-out pending query and set requests that it holds queued to the caller. Intermediate drivers should set this flag, but NIC drivers should not.

- NDIS\_ATTRIBUTE\_INTERMEDIATE\_DRIVER  
  Set if the caller is an intermediate driver.

- NDIS\_ATTRIBUTE\_IGNORE\_TOKEN\_RING\_ERRORS  
  Set if NDIS should not call a Token Ring NIC driver's *MiniportReset* function if Token Ring errors are indicated.

- NDIS\_ATTRIBUTE\_NO\_HALT\_ON\_SUSPEND  
  Set if NDIS should not call a driver's [**MiniportHalt**](https://msdn.microsoft.com/library/ff549451\(v=vs.85\)) function before the system transitions to a low-power (sleeping) state. Drivers that rely on hardware-maintained state should not set this flag.

  **Note**   Setting this flag disables the **Allow the computer to turn off this device to save power** check box in the Power Management Tab of the **Properties** dialog box for the network interface card (NIC). Power management is disabled even if the NIC is capable of power management.

- NDIS\_ATTRIBUTE\_SURPRISE\_REMOVE\_OK  
  Set if the driver can handle removal of its NIC without user notification. Such a driver exports a [**MiniportPnPEventNotify**](https://msdn.microsoft.com/library/ff550487\(v=vs.85\)) function. System support for NDIS\_ATTRIBUTE\_SURPRISE\_REMOVE\_OK is available in Windows XP and later operating systems.

- NDIS\_ATTRIBUTE\_NOT\_CO\_NDIS  
  Set by a driver that can support both connection-oriented and connectionless devices to indicate that the device is a connectionless device. System support for NDIS\_ATTRIBUTE\_NOT\_CO\_NDIS is available in Windows XP and later operating systems.

- NDIS\_ATTRIBUTE\_USES\_SAFE\_BUFFER\_APIS  
  Set by a driver that uses [**NdisBufferVirtualAddressSafe**](https://msdn.microsoft.com/library/ff550818\(v=vs.85\).md), [**NdisGetFirstBufferFromPacketSafe**](https://msdn.microsoft.com/library/ff552066\(v=vs.85\).md), and [**NdisQueryBufferSafe**](https://msdn.microsoft.com/library/ff554417\(v=vs.85\)) exclusively to access system virtual addresses for send packet buffers. NDIS\_ATTRIBUTE\_USES\_SAFE\_BUFFER\_APIS is also set by a driver that exclusively uses physical addresses to access such buffers. Setting NDIS\_ATTRIBUTE\_USES\_SAFE\_BUFFER\_APIS can improve performance since the operating system will not have to map send packet buffers to system virtual addresses. System support for NDIS\_ATTRIBUTE\_USES\_SAFE\_BUFFER\_APIS is available in Windows XP and later versions.

- NDIS\_ATTRIBUTE\_DO\_NOT\_BIND\_TO\_ALL\_CO  
  Set by a CoNDIS miniport driver that does not provide TAPI services. Setting NDIS\_ATTRIBUTE\_DO\_NOT\_BIND\_TO\_ALL\_CO prevents NDIS from binding the miniport driver to the NDIS TAPI proxy driver (NDPROXY). By default, NDIS binds NDPROXY to all CoNDIS miniport drivers.

### -param AdapterType [in, optional]

Specifies the I/O bus interface type of the caller's NIC, which usually is the type of I/O bus on which the NIC is connected, as one of the following:

- **NdisInterfaceInternal**  
  Specifies a host-specific internal interface.

- **NdisInterfaceIsa**  
  Specifies the ISA interface.

- **NdisInterfaceEisa**  
  Specifies the extended ISA (EISA) interface.

- **NdisInterfaceMca**  
  This refers to the MCA bus, which is no longer supported.

- **NdisInterfaceTurboChannel**  
  Specifies the Turbo Channel interface.

- **NdisInterfacePci**  
  Specifies the Peripheral Component Interconnect (PCI) interface.

- **NdisInterfacePcMcia**  
  Specifies the Personal Computer Memory Card International Association (PC Card) interface.

This parameter is irrelevant for intermediate drivers, which should pass zero for this argument to **NdisMSetAttributesEx**.

## -remarks

A [**MiniportInitialize**](https://msdn.microsoft.com/library/ff550472\(v=vs.85\).md) function must call **NdisMSetAttributesEx**(or [**NdisMSetAttributes**](https://msdn.microsoft.com/library/ff553619\(v=vs.85\).md)) before calling any other *NdisMRegisterXxx* or *NdisXxx* function that depends on the information supplied to **NdisMSetAttributesEx**. For example, a NIC driver's call to [**NdisMAllocateMapRegisters**](https://msdn.microsoft.com/library/ff552300\(v=vs.85\)) will fail if *MiniportInitialize* has not yet called **NdisMSetAttributesEx** with the *AttributeFlags* set with NDIS\_ATTRIBUTE\_BUS\_MASTER.

Intermediate drivers must call **NdisMSetAttributesEx**, rather than **NdisMSetAttributes**, and they must set NDIS\_ATTRIBUTE\_INTERMEDIATE\_DRIVER in the *AttributeFlags*. Setting this flag causes NDIS to treat an intermediate driver as a full-duplex miniport driver, which prevents rare but intermittent deadlocks from occurring in the intermediate driver. Consequently, every intermediate driver must be capable of handling concurrent sends and indications.

Deserialized drivers also must call **NdisMSetAttributesEx**, and they must set NDIS\_ATTRIBUTE\_DESERIALIZE in the *AttributeFlags*. NDIS does not maintain a send-packet queue for a deserialized driver, nor does NDIS serialize calls to a such a driver's *MiniportXxx* functions. A deserialized driver makes itself responsible for the following:

- Accepting all incoming send requests
- Queuing incoming send packets internally if necessary, as, for example, if a deserialized NIC driver currently has insufficient resources available to transmit an incoming send packet immediately
- Synchronizing access to its internal queue(s) as necessary among the driver's routines
- Completing all requested sends asynchronously by subsequently calling [**NdisMSendComplete**](https://msdn.microsoft.com/library/ff553613\(v=vs.85\)) with each protocol-supplied packet descriptor passed in to its **Miniport(Co)Send(Packets)** function

NDIS assumes that all connection-oriented miniports are deserialized drivers, regardless of the *AttributeFlags* that they pass to **NdisMSetAttributesEx**. That is, any driver that calls [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\)) with 0x05 as the **MajorNdisVersion** must be a deserialized miniport driver.

Serialized NIC drivers can call either of these functions from *MiniportInitialize*, but **NdisMSetAttributes** does not allow its caller to adjust the interval at which a NIC driver's [**MiniportCheckForHang**](https://msdn.microsoft.com/library/ff549367\(v=vs.85\).md) and/or [*MiniportReset*](/previous-versions/windows/embedded/aa447851(v=msdn.10)) function(s) are called.

The value of *CheckForHangTimeInSeconds* determines the NDIS library's time-out interval on sends, if any, and requests that it holds queued to the caller. By default, NDIS times out queued sends (only for serialized drivers) and requests at twice the check-for-hang interval, after which it calls the *MiniportReset* function, unless the driver sets *AttributeFlags* with NDIS\_ATTRIBUTE\_IGNORE\_PACKET\_TIMEOUT and NDIS\_ATTRIBUTE\_IGNORE\_REQUEST\_TIMEOUT when it calls **NdisMSetAttributesEx**. Intermediate drivers should set these flags when calling **NdisMSetAttributesEx** because such a driver cannot determine or control when the underlying NIC driver will process sends and requests.

NIC drivers should not set the NDIS\_ATTRIBUTE\_IGNORE\_PACKET\_TIMEOUT and NDIS\_ATTRIBUTE\_IGNORE\_REQUEST\_TIMEOUT flags, although NDIS will honor such a specification by a serialized NIC driver. However, NIC drivers can adjust the time-out interval at which their *MiniportReset* functions are called by specifying an explicit *CheckForHangTimeInSeconds*. For example, a NIC driver that emulates Ethernet over a modem might not complete every packet within the default time-out interval of the NDIS library. Whenever a packet appeared to time out on such a NIC, NDIS would assume that the NIC was no longer operating correctly and call the driver's MiniportReset function. For the driver of such a NIC, calling **NdisMSetAttributesEx** with a *CheckForHangTimeInSeconds* set to something greater than two both prevents unnecessary resets and extends the interval at which its *MiniportCheckForHang* function, if any, is called to test the operational state of the NIC.

An intermediate driver must set the NDIS\_ATTRIBUTE\_NO\_HALT\_ON\_SUSPEND flag. Setting this flag prevents NDIS from halting the driver before the system transitions to a low-power (sleeping) state.

A legacy miniport driver that manages a non-PnP-aware NIC can set the NDIS\_ATTRIBUTE\_NO\_HALT\_ON\_SUSPEND flag to prevent NDIS from halting the driver before the system transitions to a low-power state. If the miniport driver sets this flag, NDIS queries the miniport driver with [OID\_PNP\_CAPABILITIES](https://msdn.microsoft.com/library/Ff569774) even though the bus driver for the miniport driver's NIC may have indicated that the NIC is not PM-aware. The miniport driver must succeed the OID\_PNP\_CAPABILITIES request with NDIS\_STATUS\_SUCCESS. In the NDIS\_PM\_WAKE\_UP\_CAPABILITIES structure returned by this OID, the miniport driver must also specify a device power state of **NdisDeviceStateUnspecified** for each wake-up capability. When the system transitions to a low-power state, NDIS will not call such a miniport driver's *MiniportHalt* function. Before the system transitions to a lower-power state, the miniport driver must save any hardware context that it maintains. On receiving an [OID\_PNP\_SET\_POWER](https://msdn.microsoft.com/library/Ff569780) request to the D3 state, the miniport driver must set its NIC to the appropriate state for the low-power state. On receiving an OID\_PNP\_SET\_POWER request to the D0 state, the miniport driver must set its NIC to the appropriate state for the working state.

A miniport driver that supports surprise removal of its device (removal without notification through the user interface) must set NDIS\_ATTRIBUTE\_SURPRISE\_REMOVE\_OK. Doing so causes NDIS to call the driver's [**MiniportPnPEventNotify**](https://msdn.microsoft.com/library/ff550487\(v=vs.85\)) function with *PnPEvent* set to **NdisDevicePnPEventSurpriseRemoved** when the miniport's device is removed without notification. In addition, setting NDIS\_ATTRIBUTE\_SURPRISE\_REMOVE\_OK suppresses the display of a warning dialog box that asks the user to stop the device before removing it.

A miniport driver that can support both connectionless and connection-oriented devices must set NDIS\_ATTRIBUTE\_NOT\_CO\_NDIS if its device is a connectionless device. Otherwise, NDIS will mistakenly assume that its device is connection-oriented since the driver registers connection-oriented miniport driver functions with [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\)).

In general, a NIC driver must call **NdisMSetAttributesEx** before it calls any *NdisXxx* function that claims hardware resources in the registry for its NIC, because NDIS must have the *AttributeFlags* value before such a call is made and because the driver usually needs the memory at *MiniportAdapterContext* to store information for these calls. This restriction implies that a NIC driver's *MiniportInitialize* function cannot call the following *NdisXxx* before it calls **NdisMSetAttributesEx**:

- [**NdisMAllocateMapRegisters**](https://msdn.microsoft.com/library/ff552300\(v=vs.85\)) and [**NdisMAllocateSharedMemory**](https://msdn.microsoft.com/library/Ff562782)
- [**NdisMMapIoSpace**](https://msdn.microsoft.com/library/Ff563613) and, consequently, the *NdisReadRegisterXxx* and *NdisWriteRegisterXxx* functions
- [**NdisMRegisterDmaChannel**](https://msdn.microsoft.com/library/Ff563646)
- [**NdisMRegisterInterrupt**](https://msdn.microsoft.com/library/ff553596\(v=vs.85\))
- [**NdisMRegisterIoPortRange**](https://msdn.microsoft.com/library/Ff563651) and, consequently, the *NdisRaw..PortXxx* functions

However, before calling **NdisMSetAttributesEx**, any driver's *MiniportInitialize* function can call the *Ndis..Configuration* functions to retrieve configuration information installed in the registry. *MiniportInitialize* also can call the bus-type-specific *NdisReadXxx* functions, such as [**NdisReadPciSlotInformation**](https://msdn.microsoft.com/library/ff554554\(v=vs.85\)), as long as the installed registry entry for the driver's interface type matches the bus-type-specific *NdisReadXxxMiniportInitialize* calls.

The *MiniportAdapterContext* handle supplied to **NdisMSetAttributesEx** becomes an input parameter to all *MiniportXxx* functions that were registered, along with *MiniportInitialize*, in the call to [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\).md) or [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md). Usually, this handle is a pointer to resident memory, allocated by *MiniportInitialize*, in which the driver maintains NIC-specific run-time state.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563672"><strong>NdisMSetMiniportAttributes</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**MiniportInitialize**](https://msdn.microsoft.com/library/ff550472\(v=vs.85\))
- [**MiniportPnPEventNotify**](https://msdn.microsoft.com/library/ff550487\(v=vs.85\))
- [**NdisAllocateMemoryWithTag**](https://msdn.microsoft.com/library/ff550767\(v=vs.85\))
- [**NdisImmediateReadPciSlotInformation**](https://msdn.microsoft.com/library/ff552167\(v=vs.85\))
- [**NdisImmediateReadPortUchar**](https://msdn.microsoft.com/library/ff552171\(v=vs.85\))
- [**NdisImmediateReadPortUlong**](https://msdn.microsoft.com/library/ff552174\(v=vs.85\))
- [**NdisImmediateReadPortUshort**](https://msdn.microsoft.com/library/ff552177\(v=vs.85\))
- [**NdisImmediateReadSharedMemory**](https://msdn.microsoft.com/library/ff552181\(v=vs.85\))
- [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md)
- [**NdisMAllocateMapRegisters**](https://msdn.microsoft.com/library/ff552300\(v=vs.85\))
- [**NdisMAllocateSharedMemory**](https://msdn.microsoft.com/library/Ff562782)
- [**NdisMMapIoSpace**](https://msdn.microsoft.com/library/Ff563613)
- [**NdisMPciAssignResources**](https://msdn.microsoft.com/library/ff553562\(v=vs.85\))
- [**NdisMRegisterDmaChannel**](https://msdn.microsoft.com/library/Ff563646)
- [**NdisMRegisterInterrupt**](https://msdn.microsoft.com/library/ff553596\(v=vs.85\))
- [**NdisMRegisterIoPortRange**](https://msdn.microsoft.com/library/Ff563651)
- [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\))
- [**NdisOpenConfiguration**](https://msdn.microsoft.com/library/ff553676\(v=vs.85\))
- [**NdisReadEisaSlotInformation**](https://msdn.microsoft.com/library/ff554540\(v=vs.85\))
- [**NdisReadEisaSlotInformationEx**](https://msdn.microsoft.com/library/ff554544\(v=vs.85\))
