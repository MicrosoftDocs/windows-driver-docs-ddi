---
UID: NC:dot11wdi.MINIPORT_WDI_START_ADAPTER_OPERATION
title: MINIPORT_WDI_START_ADAPTER_OPERATION
author: windows-driver-content
description: The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional MiniportInitializeEx tasks.
old-location: netvista\miniportwdistartoperation.htm
old-project: netvista
ms.assetid: B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B
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
req.alt-api: (*MINIPORT_WDI_START_OPERATION_HANDLER)
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

# MINIPORT_WDI_START_ADAPTER_OPERATION callback



## -description
The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> tasks. The IHV miniport can also use it as a hint that the Microsoft component has finished initializing the miniport and the miniport can start any needed background activities.

This is an optional WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.



## -prototype

````
MINIPORT_WDI_START_ADAPTER_OPERATION MiniportWdiStartAdapterOperation;

NDIS_STATUS MiniportWdiStartAdapterOperation(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }

typedef MINIPORT_WDI_START_ADAPTER_OPERATION (*MINIPORT_WDI_START_OPERATION_HANDLER);
````


## -parameters

### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns
MiniportWdiStartAdapterOperation can return any of the following return values.
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>MiniportWdiStartAdapterOperation successfully completed. 
<dl>
<dt><b>Other NDIS_STATUS codes</b></dt>
</dl>An appropriate NDIS_STATUS code in the case of a failure.

 

To define a MiniportWdiStartAdapterOperation function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiStartAdapterOperation function that is named "MyStartOperation", use the <b>MINIPORT_WDI_START_ADAPTER_OPERATION</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_START_ADAPTER_OPERATION</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_START_ADAPTER_OPERATION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_START_ADAPTER_OPERATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

