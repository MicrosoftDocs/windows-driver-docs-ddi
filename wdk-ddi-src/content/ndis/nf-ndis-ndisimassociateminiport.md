---
UID: NF:ndis.NdisIMAssociateMiniport
title: NdisIMAssociateMiniport function (ndis.h)
description: The NdisIMAssociateMiniport function informs NDIS that the specified lower and upper interfaces for miniport and protocol drivers respectively belong to the same intermediate driver.
old-location: netvista\ndisimassociateminiport.htm
tech.root: netvista
ms.assetid: b2c46419-644b-4ad4-aa50-7c6e541638aa
ms.date: 05/02/2018
keywords: ["NdisIMAssociateMiniport function"]
ms.keywords: NdisIMAssociateMiniport, NdisIMAssociateMiniport function [Network Drivers Starting with Windows Vista], intermediate_ref_2f9545a6-262c-4347-b192-16ea23314410.xml, ndis/NdisIMAssociateMiniport, netvista.ndisimassociateminiport
f1_keywords:
 - "ndis/NdisIMAssociateMiniport"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIMAssociateMiniport
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisIMAssociateMiniport function


## -description


The
  <b>NdisIMAssociateMiniport</b> function informs NDIS that the specified lower and upper interfaces for
  miniport and protocol drivers respectively belong to the same intermediate driver.


## -parameters




### -param DriverHandle [in]

The handle to the miniport driver interface that the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function returns.


### -param ProtocolHandle [in]

The handle to the protocol interface that the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> function returns.


## -remarks



Any NDIS intermediate driver that exports both 
    <i>MiniportXxx</i> and 
    <i>ProtocolXxx</i> functions calls 
    <b>NdisIMAssociateMiniport</b> to inform the NDIS library about its miniport upper edge and its protocol
    lower edge. Such an intermediate driver calls 
    <b>NdisIMAssociateMiniport</b> during its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
    Intermediate Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>
 

 

