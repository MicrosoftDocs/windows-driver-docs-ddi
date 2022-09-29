---
UID: NF:wudfddi.IWDFMemory.GetDataBuffer
title: IWDFMemory::GetDataBuffer (wudfddi.h)
description: The GetDataBuffer method retrieves the data buffer that is associated with a memory object.
old-location: wdf\iwdfmemory_getdatabuffer.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["IWDFMemory::GetDataBuffer"]
ms.keywords: GetDataBuffer, GetDataBuffer method, GetDataBuffer method,IWDFMemory interface, IWDFMemory interface,GetDataBuffer method, IWDFMemory.GetDataBuffer, IWDFMemory::GetDataBuffer, UMDFMemoryObjectRef_910791a8-4fd9-47ff-93f9-f8f496e95272.xml, umdf.iwdfmemory_getdatabuffer, wdf.iwdfmemory_getdatabuffer, wudfddi/IWDFMemory::GetDataBuffer
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
 - IWDFMemory::GetDataBuffer
 - wudfddi/IWDFMemory::GetDataBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFMemory::GetDataBuffer
---

# IWDFMemory::GetDataBuffer

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **GetDataBuffer** method retrieves the data buffer that is associated with a memory object.

## -parameters

### -param BufferSize [out, optional]

A pointer to a variable that receives information that describes the size of the data buffer.

This parameter is optional. The driver can pass **NULL** if the driver does not require the information.

## -returns

**GetDataBuffer** returns a pointer to the data buffer.

## -remarks

For a code example of how to use the **GetDataBuffer** method, see [IWDFDevice::SetPnpState](./nf-wudfddi-iwdfdevice-setpnpstate.md).

## -see-also

- [IWDFMemory](./nn-wudfddi-iwdfmemory.md)
- [IWDFDevice::SetPnpState](./nf-wudfddi-iwdfdevice-setpnpstate.md)
