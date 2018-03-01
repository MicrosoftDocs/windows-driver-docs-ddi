---
UID: TP:netvista
ms.assetid: 81753000-e53e-3c99-bde3-5c662c944380
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Networking drivers for Windows Vista and later


Overview of the Networking drivers for Windows Vista and later technology.

To develop Networking drivers for Windows Vista and later, you need these headers:

 * [dot11wdi.h](..\dot11wdi\index.md)
 * [fwpmk.h](..\fwpmk\index.md)
 * [fwpsk.h](..\fwpsk\index.md)
 * [igpupvdev.h](..\igpupvdev\index.md)
 * [knetpwrdepbroker.h](..\knetpwrdepbroker\index.md)
 * [ndis.h](..\ndis\index.md)
 * [ndischimney.h](..\ndischimney\index.md)
 * [ndisndk.h](..\ndisndk\index.md)
 * [ndiswwan.h](..\ndiswwan\index.md)
 * [ndkpi.h](..\ndkpi\index.md)
 * [netadapter.h](..\netadapter\index.md)
 * [netdma.h](..\netdma\index.md)
 * [netioddk.h](..\netioddk\index.md)
 * [netpnp.h](..\netpnp\index.md)
 * [ntddndis.h](..\ntddndis\index.md)
 * [ntddrilapitypes.h](..\ntddrilapitypes\index.md)
 * [oemrilapitypes.h](..\oemrilapitypes\index.md)
 * [rilapi.h](..\rilapi\index.md)
 * [rilapitypes.h](..\rilapitypes\index.md)
 * [video.h](..\video\index.md)
 * [vmbuskernelmodeclientlibapi.h](..\vmbuskernelmodeclientlibapi\index.md)
 * [wditypes.hpp](..\wditypes\index.md)
 * [windot11.h](..\windot11\index.md)
 * [wlanihv.h](..\wlanihv\index.md)
 * [wlanihvtypes.h](..\wlanihvtypes\index.md)
 * [wlantypes.h](..\wlantypes\index.md)
 * [wlclient.h](..\wlclient\index.md)
 * [wsk.h](..\wsk\index.md)
 * [wwan.h](..\wwan\index.md)

For the programming guide, see [Networking drivers for Windows Vista and later](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/).

This section lists functions, callbacks, macros, structures, and enumerations used in Windows networking device drivers starting with Windows Vista. The header files that contain the topics defined in this section are included in the Windows Driver Kit (WDK).

The following sections contain information for each area of network driver technology:

## NetAdapterCx

Starting in Windows 10, version 1703, the Windows Driver Kit (WDK) includes a class extension module (NetAdapterCx) that enables you to write a KMDF-based networking (NDIS) client driver for Network Interface Cards (NICs).  The client driver interacts with NetAdapterCx, which acts as a bridge to traditional NDIS. 

For more info, see Network Adapter WDF Class Extension (Cx).

## NDIS Core Functionality

The foundation for all Windows network technologies is the Network Driver Interface Specification, or NDIS. NDIS forms the network driver platform that bridges the gap between the NIC and upper layers in the network stack.

For more info about NDIS Core Functionality, see NDIS Core Functionality.

Header files that support NDIS core functionality include the following:

- Ndis.h
- Ntddndis.h

## Scalable Networking

Windows includes technologies for scalable networking such as Header-Data Split, NetDMA, PacketDirect Provider Interface, Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload, Receive Segment Coalescing (RSC), Receive Side Scaling (RSS), and TCP/IP offload.

For more info about scalable networking, see Scalable Networking.

Header files that support scalable networking include the following:

- Ndis.h
- Ndischimney.h
- Ndisndk.h
- Ndkpi.h
- Netdma.h
- Ntddndis.h

## Virtualized Networking

NDIS supports technologies for packet transfer and management within a Hyper-V virtual environment such as Single Root I/O Virtualization (SR-IOV), Virtual Machine Queue (VMQ), and Hyper-V Extensible Switch.

For more info about virtualized networking, see  Virtualized Networking.

Header files that support virtualized networking include the following:

- Ndis.h
- Ntddndis.h
- VmbusKernelModeClientLibApi.h

## Wireless Networking

Windows network drivers support both Wi-Fi and Mobile Broadband. For Windows Vista, Windows 7, Windows 8, and Windows 8.1, Wi-Fi drivers use the Native 802.11 Wireless LAN model. For Windows 10, Wi-Fi drivers use the WLAN Universal Windows driver model, or WDI.

For more info about wireless networking, see Wireless Networking.

Header files that support wireless networking include the following:

- Dot11Wdi.h
- Ndis.h
- Ndiswwan.h
- Ntddndis.h
- Wditypes.hpp
- Windot11.h
- Wlanihv.h
- Wlantypes.h
- Wlclient.h
- Wwan.h

## Network Module Registrar

The Network Module Registrar (NMR) is an operating system module that facilitates the attachment of network modules to each other.

For more info about the NMR, see Network Module Registrar.

Header files that support the NMR include the following:

- Netioddk.h
- Wsk.h

## Winsock Kernel (WSK)

Winsock Kernel (WSK) is the kernel mode component of Windows Sockets. 

For more info about WSK, see Winsock Kernel.

Header files that support WSK include the following:

- Wsk.h

## Windows Filtering Platform Callout Drivers

Windows Filtering Platform Callout Drivers are network drivers that implement one or more callouts, which enable them to process TCP/IP-based network data in ways that are beyond simple filtering.

For more info about Windows Filtering Platform Callout Drivers, see Windows Filtering Platform Callout Drivers.

Header files that support Windows Filtering Platform Callout Drivers include the following:

- Fwpmk.h
- Fwpsk.h

Send comments about this topic to Microsoft

