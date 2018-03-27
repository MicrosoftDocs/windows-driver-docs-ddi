---
UID: NF:ndis.NdisFDeregisterFilterDriver
title: NdisFDeregisterFilterDriver function
author: windows-driver-content
description: A filter drivers calls the NdisFDeregisterFilterDriver function to release resources that it previously allocated with the NdisFRegisterFilterDriver function.
old-location: netvista\ndisfderegisterfilterdriver.htm
old-project: netvista
ms.assetid: f97ecce3-73b9-4c51-b4a4-e114420af2c9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFDeregisterFilterDriver, NdisFDeregisterFilterDriver function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_d158c9c1-1e83-464f-b00a-421b658c8c32.xml, ndis/NdisFDeregisterFilterDriver, netvista.ndisfderegisterfilterdriver
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
req.ddi-compliance: Irql_Filter_Driver_Function, NdisFDeregisterFilterDriver
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
-	NdisFDeregisterFilterDriver
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFDeregisterFilterDriver function


## -description


A filter drivers calls the
  <b>NdisFDeregisterFilterDriver</b> function to release resources that it previously allocated with the 
  <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
  NdisFRegisterFilterDriver</a> function.


## -parameters




### -param NdisFilterDriverHandle [in]

The filter driver handle that identifies this filter driver. NDIS returned the handle to the
     filter driver in a call to 
     <b>NdisFRegisterFilterDriver</b>.


## -returns



None




## -remarks



A filter driver must call 
    <b>NdisFDeregisterFilterDriver</b> from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff549936">FilterDriverUnload</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549936">FilterDriverUnload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFDeregisterFilterDriver function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

