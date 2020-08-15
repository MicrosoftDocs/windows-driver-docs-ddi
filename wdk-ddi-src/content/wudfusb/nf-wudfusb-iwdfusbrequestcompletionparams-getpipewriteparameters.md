---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetPipeWriteParameters
title: IWDFUsbRequestCompletionParams::GetPipeWriteParameters (wudfusb.h)
description: The GetPipeWriteParameters method retrieves parameters that are associated with the completion of a write request.
old-location: wdf\iwdfusbrequestcompletionparams_getpipewriteparameters.htm
tech.root: wdf
ms.assetid: c6824215-0c16-471e-aea9-1b5cbeb2286b
ms.date: 02/26/2018
keywords: ["IWDFUsbRequestCompletionParams::GetPipeWriteParameters"]
ms.keywords: GetPipeWriteParameters, GetPipeWriteParameters method, GetPipeWriteParameters method,IWDFUsbRequestCompletionParams interface, IWDFUsbRequestCompletionParams interface,GetPipeWriteParameters method, IWDFUsbRequestCompletionParams.GetPipeWriteParameters, IWDFUsbRequestCompletionParams::GetPipeWriteParameters, UMDFRequestObjectRef_430256d1-89c8-4ef7-9385-8ae29d848f57.xml, umdf.iwdfusbrequestcompletionparams_getpipewriteparameters, wdf.iwdfusbrequestcompletionparams_getpipewriteparameters, wudfusb/IWDFUsbRequestCompletionParams::GetPipeWriteParameters
f1_keywords:
 - "wudfusb/IWDFUsbRequestCompletionParams.GetPipeWriteParameters"
 - "IWDFUsbRequestCompletionParams.GetPipeWriteParameters"
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUsbRequestCompletionParams.GetPipeWriteParameters
targetos: Windows
req.typenames: 
---

# IWDFUsbRequestCompletionParams::GetPipeWriteParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPipeWriteParameters</b> method retrieves parameters that are associated with the completion of a write request.


## -parameters




### -param ppWriteMemory 
[out, optional]
A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface, for access to the write buffer for the write request. This parameter is optional and can be <b>NULL</b>.


### -param pBytesWritten 
[out, optional]
A pointer to a variable that receives the size, in bytes, of the write buffer for the write request. This parameter is optional and can be <b>NULL</b>.


### -param pWriteMemoryOffset 
[out, optional]
A pointer to a variable that receives the offset, in bytes, into the write buffer for the write request. This parameter is optional and can be <b>NULL</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbrequestcompletionparams">IWDFUsbRequestCompletionParams</a>
 

 

