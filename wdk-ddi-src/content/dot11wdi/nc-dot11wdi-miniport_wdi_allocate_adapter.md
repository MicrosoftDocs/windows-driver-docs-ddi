---
UID: NC:dot11wdi.MINIPORT_WDI_ALLOCATE_ADAPTER
title: MINIPORT_WDI_ALLOCATE_ADAPTER
author: windows-driver-content
description: The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.
old-location: netvista\miniportwdiallocateadapter.htm
old-project: netvista
ms.assetid: 4CBC7230-6480-40C9-90B7-A286FCEB1FA8
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
req.alt-api: MiniportWdiAllocateAdapter
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

# MINIPORT_WDI_ALLOCATE_ADAPTER callback



## -description
The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.



## -prototype

````
MINIPORT_WDI_ALLOCATE_ADAPTER MiniportWdiAllocateAdapter;

NDIS_STATUS MiniportWdiAllocateAdapter(
  _In_    NDIS_HANDLE                                    NdisMiniportHandle,
  _In_    NDIS_HANDLE                                    MiniportDriverContext,
  _In_    PNDIS_MINIPORT_INIT_PARAMETERS                 MiniportInitParameters,
  _In_    PNDIS_WDI_INIT_PARAMETERS                      NdisWdiInitParameters,
  _Inout_ PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES RegistrationAttributes
)
{ ... }
````


## -parameters

### -param NdisMiniportHandle [in]

The NDIS-supplied handle that identifies the miniport adapter.


### -param MiniportDriverContext [in]

The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the <a href="..\dot11wdi\nf-dot11wdi-ndismregisterwdiminiportdriver.md">NdisMRegisterWdiMiniportDriver</a> function.




### -param MiniportInitParameters [in]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the miniport adapter.


### -param NdisWdiInitParameters [in]

A pointer to an <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a> structure that defines the WDI initialization parameters for the miniport adapter.


### -param RegistrationAttributes [in, out]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure that defines registration attributes that are associated with the miniport adapter.


## -returns

            MiniportWdiAllocateAdapter can return any of the following return values.
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>MiniportWdiAllocateAdapter successfully completed.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>MiniportWdiAllocateAdapter could not allocate the necessary resources.

 

To define a MiniportWdiAllocateAdapter function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiAllocateAdapter function that is named "MyAllocateAdapter", use the <b>MINIPORT_WDI_ALLOCATE_ADAPTER</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_ALLOCATE_ADAPTER</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_ALLOCATE_ADAPTER</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_ALLOCATE_ADAPTER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

