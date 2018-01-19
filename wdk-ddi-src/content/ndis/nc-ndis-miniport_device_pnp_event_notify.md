---
UID: NC:ndis.MINIPORT_DEVICE_PNP_EVENT_NOTIFY
title: MINIPORT_DEVICE_PNP_EVENT_NOTIFY
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportDevicePnPEventNotify function to notify the driver of Plug and Play (PnP) events.
old-location: netvista\miniportdevicepnpeventnotify.htm
old-project: netvista
ms.assetid: e41240c0-17be-42ef-a72c-c5311115cf64
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportDevicePnPEventNotify
req.alt-loc: Ndis.h
req.ddi-compliance: NdisOidComplete
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_DEVICE_PNP_EVENT_NOTIFY callback



## -description
NDIS calls a miniport driver's 
   <i>MiniportDevicePnPEventNotify</i> function to notify the driver of Plug and Play
   (PnP) events.



## -prototype

````
MINIPORT_DEVICE_PNP_EVENT_NOTIFY MiniportDevicePnPEventNotify;

VOID MiniportDevicePnPEventNotify(
  _In_ NDIS_HANDLE           MiniportAdapterContext,
  _In_ PNET_DEVICE_PNP_EVENT NetDevicePnPEvent
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for an miniport adapter.


### -param NetDevicePnPEvent [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_device_pnp_event.md">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.


## -returns
None


## -remarks
A driver specifies the 
    <i>MiniportDevicePnPEventNotify</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function.

NDIS calls the driver's 
    <i>MiniportDevicePnPEventNotify</i> function with the 
    <b>DevicePnPEvent</b> member of the 
    <i>NetDevicePnPEvent</i> parameter set to
    <b>NdisDevicePnPEventPowerProfileChanged</b> after one of the following events:

Driver initialization is complete.

The driver received an 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a> notification that
      specifies the powered-on state (
      <b>NdisDeviceStateD0</b>).

In the second case, the value at 
    <i>InformationBuffer</i> indicates whether the system is running on battery power (<b>NdisPowerProfileBattery</b>) or AC power (<b>NdisPowerProfileAcOnline</b>). A driver can use this information to adjust the power consumption of
    the specified miniport adapter. For example, the driver for a wireless LAN device could reduce power
    consumption if the system is running on battery power or increase power consumption if the system is
    running on AC power.

When a driver receives a surprise removal notification (the 
    <b>DevicePnPEvent</b> member of the 
    <i>NetDevicePnPEvent</i> parameter is 
    <b>NdisDevicePnPEventSurpriseRemoved</b>), it should:

Note internally that the device has been removed.

Cancel any pending IRPs that it sent down to the underlying bus driver.

After NDIS calls the 
    <i>MiniportDevicePnPEventNotify</i> function to indicate a surprise removal, NDIS
    calls the driver's 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. If the driver
    receives any send requests or OID requests before NDIS calls 
    <i>MiniportHaltEx</i>, it should immediately complete such requests with a status
    value of NDIS_STATUS_NOT_ACCEPTED.

NDIS calls 
    <i>MiniportDevicePnPEventNotify</i> at IRQL = PASSIVE_LEVEL.

To define a <i>MiniportDevicePnPEventNotify</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDevicePnPEventNotify</i> function that is named "MyDevicePnPEventNotify", use the <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_device_pnp_event.md">NET_DEVICE_PNP_EVENT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_DEVICE_PNP_EVENT_NOTIFY callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

