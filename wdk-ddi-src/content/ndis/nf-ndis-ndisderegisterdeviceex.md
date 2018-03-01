---
UID: NF:ndis.NdisDeregisterDeviceEx
title: NdisDeregisterDeviceEx function
author: windows-driver-content
description: The NdisDeregisterDeviceEx function removes, from the system, a device object that was created by the NdisRegisterDeviceEx function.
old-location: netvista\ndisderegisterdeviceex.htm
old-project: netvista
ms.assetid: bca1ef90-b574-4ed5-a9ec-c553372490b1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisDeregisterDeviceEx, NdisDeregisterDeviceEx function [Network Drivers Starting with Windows Vista], ndis/NdisDeregisterDeviceEx, ndis_devices_ref_40ed1b6b-39ce-43fc-ae0d-8371eab300d7.xml, netvista.ndisderegisterdeviceex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
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
-	NdisDeregisterDeviceEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDeregisterDeviceEx function


## -description


The 
  <b>NdisDeregisterDeviceEx</b> function removes, from the system, a device object that was created by the 
  <a href="..\ndis\nf-ndis-ndisregisterdeviceex.md">NdisRegisterDeviceEx</a> function.


## -syntax


````
VOID NdisDeregisterDeviceEx(
  _In_ NDIS_HANDLE NdisDeviceHandle
);
````


## -parameters




### -param NdisDeviceHandle [in]

The handle returned by 
     <a href="..\ndis\nf-ndis-ndisregisterdeviceex.md">NdisRegisterDeviceEx</a> that identifies
     the device object to be deregistered.


## -returns



None




## -remarks



The 
    <b>NdisDeregisterDeviceEx</b> function removes a device object that was created by the 
    <a href="..\ndis\nf-ndis-ndisregisterdeviceex.md">NdisRegisterDeviceEx</a> function. 
    <b>NdisDeregisterDeviceEx</b> also removes the symbolic link that is associated with this device
    object.




## -see-also

<a href="..\ndis\nf-ndis-ndisregisterdeviceex.md">NdisRegisterDeviceEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeregisterDeviceEx function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

