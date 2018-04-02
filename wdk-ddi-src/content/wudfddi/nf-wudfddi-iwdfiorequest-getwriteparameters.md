---
UID: NF:wudfddi.IWDFIoRequest.GetWriteParameters
title: IWDFIoRequest::GetWriteParameters method
author: windows-driver-content
description: The GetWriteParameters method retrieves the request parameters for a write-type request.
old-location: wdf\iwdfiorequest_getwriteparameters.htm
old-project: wdf
ms.assetid: 0627b278-2fd5-4185-8ec9-8b306c6d85a8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetWriteParameters method, GetWriteParameters method, IWDFIoRequest interface, GetWriteParameters,IWDFIoRequest.GetWriteParameters, IWDFIoRequest, IWDFIoRequest interface, GetWriteParameters method, IWDFIoRequest::GetWriteParameters, UMDFRequestObjectRef_1aa8b098-4652-435b-beb7-5b7be69fd5d0.xml, umdf.iwdfiorequest_getwriteparameters, wdf.iwdfiorequest_getwriteparameters, wudfddi/IWDFIoRequest::GetWriteParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.GetWriteParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetWriteParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves the request parameters for a write-type request.


## -parameters




### -param pSizeInBytes [out]

A pointer to a variable that receives the size, in bytes, to write. To retrieve the data for writing, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pullOffset




### -param pulKey [out]

A pointer to a variable that receives a key that the driver can use to sort the I/O request in a way that the driver determines. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


#### - pllOffset [out]

A pointer to a variable that receives the offset, in bytes, to begin writing to the device or the file on the device. If the device does not support absolute write addresses, <i>pllOffset</i> can be ignored. For more information, see the following Remarks section.

Client applications specify this value in the <b>Offset</b> and <b>OffsetHigh</b> members of the OVERLAPPED structure. A pointer to OVERLAPPED is passed in the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -remarks



A call to <b>GetWriteParameters</b> fails if the request type is not a write type.

For devices that support addressing (for example, a disk device), the value that the <i>pllOffset</i> parameter points to is typically the byte offset into the device. For devices that do not support addressing (for example, a serial port), the driver can ignore the value at <i>pllOffset</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>
 

 

