---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_INITIALIZE
title: MINIPORT_WDI_TAL_TXRX_INITIALIZE
author: windows-driver-content
description: The MiniportWdiTalTxRxInitialize handler function initializes data structures in the TAL and exchanges datapath component handles between the UE and TAL.
old-location: netvista\miniportwditaltxrxinitialize.htm
old-project: netvista
ms.assetid: C297D681-D43F-4105-9E08-7FF42807E9A0
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
req.alt-api: MiniportWdiTalTxRxInitialize
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

# MINIPORT_WDI_TAL_TXRX_INITIALIZE callback



## -description
The 
  MiniportWdiTalTxRxInitialize handler function initializes data structures in the TAL and exchanges datapath component handles between the UE and TAL. This is issued in the context of the driver initialization, and is issued prior to querying the firmware for the device capabilities.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.



## -prototype

````
MINIPORT_WDI_TAL_TXRX_INITIALIZE MiniportWdiTalTxRxInitialize;

NDIS_STATUS MiniportWdiTalTxRxInitialize(
  _In_    NDIS_HANDLE                      MiniportAdapterContext,
  _In_    NDIS_HANDLE                      NdisMiniportDataPathHandle,
  _In_    PNDIS_WDI_DATA_API               NdisWdiDataPathApi,
  _Out_   PTAL_TXRX_HANDLE                 pMiniportTalTxRxContext,
  _Inout_ PNDIS_MINIPORT_WDI_DATA_HANDLERS pMiniportDataHandlers,
  _Out_   UINT32                           *pMiniportWdiFrameMetadataExtraSpace
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

Handle for the IHV miniport context.


### -param NdisMiniportDataPathHandle [in]

Handle for the IHV miniport to use in datapath indications.


### -param NdisWdiDataPathApi [in]

Pointer to the WDI data API function table.


### -param pMiniportTalTxRxContext [out]

The TAL device handle is a control path handle for the device (for example, MiniportContext). It is associated with the MiniportHandle, which used as context for NDIS API calls.


### -param pMiniportDataHandlers [in, out]

The UE initializes the NDIS Header field so the LE can determine the revision and size that is safe to initialize according to traditional NDIS versioning rules.  The LE is responsible for updating the Header with the revision and size that the LE actually implements and supports before returning.


### -param pMiniportWdiFrameMetadataExtraSpace [out]

The LE sets the value pointed to by this parameter to the amount of space that WDI should reserve after the <a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a> for the LE to use.


## -returns
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the miniport driver successfully exchanged datapath component handles.

 

To define a MiniportWdiTalTxRxInitialize function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTalTxRxInitialize function that is named "MyTalTxRxInitialize", use the <b>MINIPORT_WDI_TAL_TXRX_INITIALIZE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_TAL_TXRX_INITIALIZE</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TAL_TXRX_INITIALIZE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TAL_TXRX_INITIALIZE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

