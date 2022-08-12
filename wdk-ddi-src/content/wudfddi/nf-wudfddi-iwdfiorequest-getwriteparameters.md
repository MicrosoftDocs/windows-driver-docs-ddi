---
UID: NF:wudfddi.IWDFIoRequest.GetWriteParameters
title: IWDFIoRequest::GetWriteParameters (wudfddi.h)
description: The GetWriteParameters method retrieves the request parameters for a write-type request.
old-location: wdf\iwdfiorequest_getwriteparameters.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["IWDFIoRequest::GetWriteParameters"]
ms.keywords: GetWriteParameters, GetWriteParameters method, GetWriteParameters method,IWDFIoRequest interface, IWDFIoRequest interface,GetWriteParameters method, IWDFIoRequest.GetWriteParameters, IWDFIoRequest::GetWriteParameters, UMDFRequestObjectRef_1aa8b098-4652-435b-beb7-5b7be69fd5d0.xml, umdf.iwdfiorequest_getwriteparameters, wdf.iwdfiorequest_getwriteparameters, wudfddi/IWDFIoRequest::GetWriteParameters
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest::GetWriteParameters
 - wudfddi/IWDFIoRequest::GetWriteParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest::GetWriteParameters
---

# IWDFIoRequest::GetWriteParameters

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **GetWriteParameters** method retrieves the request parameters for a write-type request.

## -parameters

### -param pSizeInBytes [out, optional]

A pointer to a variable that receives the size, in bytes, to write. To retrieve the data for writing, the driver calls the [IWDFIoRequest::GetInputMemory](./nf-wudfddi-iwdfiorequest-getinputmemory.md) method.

This parameter is optional. The driver can pass **NULL** if it does not require the information.

### -param pullOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, to begin writing to the device or the file on the device. If the device does not support absolute write addresses, *pullOffset* can be ignored. For more information, see the following Remarks section.

Client applications specify this value in the **Offset** and **OffsetHigh** members of the OVERLAPPED structure. A pointer to OVERLAPPED is passed in the Microsoft Win32 **WriteFile** or **WriteFileEx** function.

This parameter is optional. The driver can pass **NULL** if it does not require the information.

### -param pulKey [out, optional]

A pointer to a variable that receives a key that the driver can use to sort the I/O request in a way that the driver determines.

This parameter is optional. The driver can pass **NULL** if it does not require the information.

## -remarks

A call to **GetWriteParameters** fails if the request type is not a write type.

For devices that support addressing (for example, a disk device), the value that the *pullOffset* parameter points to is typically the byte offset into the device. For devices that do not support addressing (for example, a serial port), the driver can ignore the value at *pullOffset*.

## -see-also

- [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md)
- [IWDFIoRequest::GetInputMemory](./nf-wudfddi-iwdfiorequest-getinputmemory.md)
