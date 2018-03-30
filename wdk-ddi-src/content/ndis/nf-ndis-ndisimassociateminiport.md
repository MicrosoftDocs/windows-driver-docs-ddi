---
UID: NF:ndis.NdisIMAssociateMiniport
title: NdisIMAssociateMiniport function
author: windows-driver-content
description: The NdisIMAssociateMiniport function informs NDIS that the specified lower and upper interfaces for miniport and protocol drivers respectively belong to the same intermediate driver.
old-location: netvista\ndisimassociateminiport.htm
old-project: netvista
ms.assetid: b2c46419-644b-4ad4-aa50-7c6e541638aa
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisIMAssociateMiniport, NdisIMAssociateMiniport function [Network Drivers Starting with Windows Vista], intermediate_ref_2f9545a6-262c-4347-b192-16ea23314410.xml, ndis/NdisIMAssociateMiniport, netvista.ndisimassociateminiport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIMAssociateMiniport
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisIMAssociateMiniport function


## -description


The
  <b>NdisIMAssociateMiniport</b> function informs NDIS that the specified lower and upper interfaces for
  miniport and protocol drivers respectively belong to the same intermediate driver.


## -parameters




### -param DriverHandle [in]

The handle to the miniport driver interface that the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> function returns.


### -param ProtocolHandle [in]

The handle to the protocol interface that the 
     <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
     NdisRegisterProtocolDriver</a> function returns.


## -returns



None




## -remarks



Any NDIS intermediate driver that exports both 
    <i>MiniportXxx</i> and 
    <i>ProtocolXxx</i> functions calls 
    <b>NdisIMAssociateMiniport</b> to inform the NDIS library about its miniport upper edge and its protocol
    lower edge. Such an intermediate driver calls 
    <b>NdisIMAssociateMiniport</b> during its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
    Intermediate Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIMAssociateMiniport function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
