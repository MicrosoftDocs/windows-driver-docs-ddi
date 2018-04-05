---
UID: NF:ndis.NdisFIndicateStatus
title: NdisFIndicateStatus function
author: windows-driver-content
description: The NdisFIndicateStatus function passes on a filtered status indication from an underlying driver or originates a status indication.
old-location: netvista\ndisfindicatestatus.htm
old-project: netvista
ms.assetid: fd81d777-8479-41e3-8f71-e5f4134b60a0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFIndicateStatus, NdisFIndicateStatus function [Network Drivers Starting with Windows Vista], ndis/NdisFIndicateStatus, ndis_status_ref_e649b130-878b-4019-b377-dd099de6eb8e.xml, netvista.ndisfindicatestatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_StatusIndication_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFIndicateStatus
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFIndicateStatus function


## -description


The 
  <b>NdisFIndicateStatus</b> function passes on a filtered status indication from an underlying driver or
  originates a status indication.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns



None




## -remarks



Filter drivers can call 
    <b>NdisFIndicateStatus</b> from the 
    <a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a> function, to pass on a
    filtered status indication to overlying drivers.

To originate status indications, filter drivers call 
    <b>NdisFIndicateStatus</b> without a prior NDIS call to 
    <i>FilterStatus</i>.

A filter driver can call 
    <b>NdisFIndicateStatus</b> after setting its registration attributes and the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562619">NdisFSetAttributes</a> function returns.
    The driver must not call 
    <b>NdisFIndicateStatus</b> after it returns from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a>



<a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562619">NdisFSetAttributes</a>
 

 

