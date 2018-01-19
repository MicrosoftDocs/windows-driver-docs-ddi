---
UID: NC:dot11wdi.MINIPORT_WDI_IDLE_NOTIFICATION
title: MINIPORT_WDI_IDLE_NOTIFICATION
author: windows-driver-content
description: NDIS calls the MiniportWdiIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.
old-location: netvista\miniportwdiidlenotification.htm
old-project: netvista
ms.assetid: BA050C7C-A593-469E-9212-B363F2D2A409
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _SYNTH_STATS, SYNTH_STATS, *PSYNTH_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportWdiIdleNotification
req.alt-loc: dot11wdi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_IDLE_NOTIFICATION callback



## -description
NDIS calls the MiniportWdiIdleNotification handler   function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.



## -prototype

````
MINIPORT_WDI_IDLE_NOTIFICATION MiniportWdiIdleNotification;

NDIS_STATUS MiniportWdiIdleNotification(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ BOOLEAN     ForceIdle
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param ForceIdle [in]

A BOOLEAN value that, when set to TRUE, specifies that the miniport driver must not veto the idle notification and must continue with the low-power state transition.

For more information about the ForceIdle parameter, see the Remarks section.



## -returns

            MiniportWdiIdleNotification can return any of the following return values.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The miniport driver successfully handled the idle notification. The notification is left in a pending state until the miniport driver calls <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_complete.md">NdisWdiIdleNotificationComplete</a>.
<dl>
<dt><b>NDIS_STATUS_BUSY</b></dt>
</dl>
       The miniport driver vetoed the idle notification because the network adapter is still being used.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The miniport driver could not issue a bus-specific IRP successfully.

 

To define a MiniportWdiIdleNotification function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiIdleNotification function that is named "MyIdleNotification", use the <b>MINIPORT_WDI_IDLE_NOTIFICATION</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_IDLE_NOTIFICATION</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_IDLE_NOTIFICATION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_complete.md">NdisWdiIdleNotificationComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_IDLE_NOTIFICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

