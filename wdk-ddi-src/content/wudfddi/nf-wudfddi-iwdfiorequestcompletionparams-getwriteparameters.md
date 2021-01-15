---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetWriteParameters
title: IWDFIoRequestCompletionParams::GetWriteParameters (wudfddi.h)
description: The GetWriteParameters method retrieves parameters that are associated with the completion of a write request.
old-location: wdf\iwdfiorequestcompletionparams_getwriteparameters.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoRequestCompletionParams::GetWriteParameters"]
ms.keywords: GetWriteParameters, GetWriteParameters method, GetWriteParameters method,IWDFIoRequestCompletionParams interface, IWDFIoRequestCompletionParams interface,GetWriteParameters method, IWDFIoRequestCompletionParams.GetWriteParameters, IWDFIoRequestCompletionParams::GetWriteParameters, UMDFRequestObjectRef_018d6259-d6c5-4004-966a-6d18bca94057.xml, umdf.iwdfiorequestcompletionparams_getwriteparameters, wdf.iwdfiorequestcompletionparams_getwriteparameters, wudfddi/IWDFIoRequestCompletionParams::GetWriteParameters
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
 - IWDFIoRequestCompletionParams::GetWriteParameters
 - wudfddi/IWDFIoRequestCompletionParams::GetWriteParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequestCompletionParams::GetWriteParameters
---

# IWDFIoRequestCompletionParams::GetWriteParameters


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves parameters that are associated with the completion of a write request.

## -parameters

### -param ppWriteMemory 

[out]
A pointer to a variable that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for access to the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

### -param pBytesWritten 

[out]
A pointer to a variable that receives the size, in bytes, of the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

### -param pWriteMemoryOffset 

[out]
A pointer to a variable that receives the offset, in bytes, into the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequestcompletionparams">IWDFIoRequestCompletionParams</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>

