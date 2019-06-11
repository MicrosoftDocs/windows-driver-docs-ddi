---
UID: NF:ks.KsCreatePin
title: KsCreatePin function (ks.h)
description: The KsCreatePin function passes a connection request to a device, creating a pin instance. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.
old-location: stream\kscreatepin.htm
tech.root: stream
ms.assetid: 0dae335a-bcc1-4f6a-8926-e2ecc4112dc5
ms.date: 04/23/2018
ms.keywords: KsCreatePin, KsCreatePin function [Streaming Media Devices], ks/KsCreatePin, ksfunc_f49fab36-1309-4eec-addb-4eba94583692.xml, stream.kscreatepin
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- ks.lib
- ks.dll
- ksuser.dll
api_name:
- KsCreatePin
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreatePin function


## -description


The <b>KsCreatePin</b> function passes a connection request to a device, creating a pin instance. This function can only be called at <b>PASSIVE_LEVEL</b> for kernel-mode clients.


## -parameters




### -param FilterHandle [in]

Specifies the handle of the filter initiating the create request and where the connection will occur. 


### -param Connect [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563531">KSPIN_CONNECT</a> structure that contains parameters for the requested connection. This should be followed in memory by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> data structure, describing the data format requested for the connection.


### -param DesiredAccess [in]

Specifies the access desired to the pin. This is typically <b>GENERIC_READ</b> or <b>GENERIC_WRITE</b>. For data flowing into the pin this value should be set to <b>GENERIC_WRITE</b>, and for data flowing out of the pin this should be set to <b>GENERIC_READ</b> regardless of the communication method.


### -param ConnectionHandle [out]

Specifies the connection handle passed. The routine fills this in with a handle to the file object of the created connection. This value can then be used to disconnect with the <a href="https://msdn.microsoft.com/9b84891d-62ca-4ddc-97b7-c4c79482abd9">CloseHandle</a> function.


## -returns



The <b>KsCreatePin</b> function returns <b>STATUS_SUCCESS</b> if the connection was successful, or it returns an error if the connection failed. Additionally, this Win32 error code (from Winerror.h) can be returned:




## -remarks



The routine sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request to the driver. The driver accepts the request only if the interface, medium, and data format are compatible.

If <i>Connect</i>-><b>PinToHandle</b> is <b>NULL</b>, <b>KsCreatePin</b> creates a pin the caller can use to send requests to the streaming driver specified in <i>Connect</i>-><b>FilterHandle</b>. <i>Connect</i>-><b>PinId</b> determines the pin type of the pin to be created.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563531">KSPIN_CONNECT</a>
 

 

